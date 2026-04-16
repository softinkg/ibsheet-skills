# 트리 구조

## 트리 컬럼 설정

트리 구조는 기존 컬럼에 `TreeCol:1` 속성을 추가하여 사용합니다.

```javascript
{Header:"부서", Type:"Text", SaveName:"DEPT", TreeCol:1, Width:250,
  LevelSaveName:"TREELEVEL",    // 레벨 저장명
  TreeCheck:1,                   // 트리 체크박스
  CheckSaveName:"TCheck",       // 체크 저장명
  Edit:0}
```

### 트리 관련 Cfg 설정
```javascript
initData.Cfg = {
  SearchMode: smLazyLoad,
  ChildPage: 5   // 트리 자식 페이지 수
};
```

---

## 트리 데이터 형식

Level 필드로 계층을 지정합니다.
```json
{
  "Data": [
    {"Level":0, "DEPT":"본사"},
    {"Level":1, "DEPT":"기획팀"},
    {"Level":2, "DEPT":"기획1파트"},
    {"Level":1, "DEPT":"개발팀"},
    {"Level":2, "DEPT":"개발1파트"}
  ]
}
```

---

## 트리 제어 API

### ShowTreeLevel(level, childOpen)
트리 레벨별 접기/펼치기를 제어합니다.
```javascript
mySheet.ShowTreeLevel(level, childOpen);
// level: 0(모두 접기), -1(모두 펼치기), 1~N(해당 레벨까지)
// childOpen: 0(이전상태유지), 1(모두 접음), 2(모두 펼침)
```

### SetTreeActionMode(mode)
삭제 동작 모드를 설정합니다.
```javascript
mySheet.SetTreeActionMode(0);  // 자식 있으면 삭제 불가
mySheet.SetTreeActionMode(1);  // 삭제 시 자식까지 삭제
```

### SetTreeCheckActionMode(mode)
트리 체크 연관 동작을 설정합니다.
```javascript
mySheet.SetTreeCheckActionMode(1);  // 부모 체크 시 자식도 체크
```

### 트리 연결선
```javascript
mySheet.NoTreeLines = false;  // 연결선 표시
```

---

## 트리 이벤트

### OnBeforeExpand / OnAfterExpand
트리 노드 접기/펼치기 시 호출됩니다.
```javascript
function mySheet_OnBeforeExpand(row, expand) {}
function mySheet_OnAfterExpand(row, expand) {}
```

### OnTreeChild (동적 트리)
자식 노드를 동적으로 로드할 때 사용합니다.
```javascript
function mySheet_OnTreeChild(row) {
  mySheet.DoSearchChild("child_data.jsp", row, {Param:"parentId=" + mySheet.GetCellValue(row, "ID")});
}
```

---

## 트리 소계

### ShowTreeSubSum
트리 구조에서 소계를 표시합니다.
```javascript
mySheet.ShowTreeSubSum();
```

### SetRowLevel
행의 트리 레벨을 설정합니다.
```javascript
mySheet.SetRowLevel(row, level);
```

---

## 예제: 트리 초기화 및 조회

> 출처: `docs/examples/07/tree.html`

```javascript
function LoadPage() {
  mySheet.Reset();
  var initData = {};
  initData.Cfg = {SearchMode:smLazyLoad, ChildPage:5};
  initData.Cols = [
    {Header:"상태", Type:"Status", Align:"Center"},
    {Header:"삭제", Type:"DelCheck", Align:"Center"},
    {Header:"구/동", Type:"Text", SaveName:"GUDONG", Width:250,
      TreeCol:1,
      LevelSaveName:"TREELEVEL",
      TreeCheck:true,
      CheckSaveName:"TCheck",
      Edit:0},
    {Header:"우편번호", Type:"Text", SaveName:"POSTNO", Width:65, Format:"PostNo"},
    {Header:"주소", Type:"Text", SaveName:"ADDR", Width:370, MultiLineText:1, Wrap:1}
  ];
  IBS_InitSheet(mySheet, initData);

  mySheet.SetTreeCheckActionMode(1);
  mySheet.SetActionMenu("행추가|엑셀다운");
  mySheet.NoTreeLines = false;

  doAction('search');
}

// 조회
mySheet.DoSearch("tree_data_json.jsp");
```

### 트리 레벨 제어
```javascript
// 모두 접기
mySheet.ShowTreeLevel(0, 0);

// 모두 펼치기
mySheet.ShowTreeLevel(-1, 0);

// 2레벨까지 펼치기
mySheet.ShowTreeLevel(2, 1);
```

### 트리 데이터 (JSON)
```json
{
  "Data": [
    {"Level":0, "GUDONG":"서울특별시", "POSTNO":""},
    {"Level":1, "GUDONG":"강남구", "POSTNO":"135"},
    {"Level":2, "GUDONG":"역삼동", "POSTNO":"135-080"}
  ]
}
```
