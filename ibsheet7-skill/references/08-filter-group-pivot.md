# 필터/그룹/소계/피벗

## 필터 (Filter)

### 필터 행 표시/숨김
```javascript
mySheet.ShowFilterRow();     // 필터 행 표시
mySheet.HideFilterRow();     // 필터 행 숨김
mySheet.FindFilterRow();     // 필터 행 존재 여부 (>0: 존재)
```

### 프로그래밍 방식 필터
```javascript
mySheet.SetFilterValue(col, value, matchType, applyNow);
// matchType: 1(포함), 11(일치) 등
```

### 필터 이벤트
```javascript
function mySheet_OnFilterEnd(RowCnt, FirstRow) {
  console.log("[OnFilterEnd] RowCnt:" + RowCnt + ", FirstRow:" + FirstRow);
}
```

---

## 그룹 (Group)

### 그룹 행 표시/숨김
```javascript
// 그룹 행 표시 (헤더에서 드래그로 그룹 지정)
mySheet.ShowGroupRow("", "{%s} <font color='red'>(<b>{%c}</b>건)</font>");
mySheet.HideGroupRow();
```

### 그룹 관련 Cfg 설정
```javascript
initSheet.Cfg = {UseGroupActionMenu: 1};  // 그룹 우클릭 메뉴 사용
```

### Cols에서 GroupSumType 설정
```javascript
{Header:"용량", Type:"AutoSum", SaveName:"qty", GroupSumType:"Sum"}
```

### 그룹 이벤트
```javascript
function mySheet_OnGroupFinish(Group) {
  if (Group) {
    mySheet.SetSelectRow(1);
  } else {
    mySheet.ColumnSort();
  }
}
```

---

## 소계 (SubSum)

### ShowSubSum(배열)
```javascript
// 단일 컬럼 소계
mySheet.ShowSubSum([
  {StdCol:"DEPT", SumCols:"AMT1|AMT2", Sort:"asc", CaptionCol:"DEPT"}
]);

// 다중 컬럼 소계
mySheet.ShowSubSum([
  {StdCol:0, SumCols:"6|7", ShowCumulate:0, Sort:0},
  {StdCol:1, SumCols:"2|3|4|5", ShowCumulate:0, Sort:0, CaptionCol:1, OtherColText:"0=%s"}
]);

// 개수+합계+평균 동시 소계
mySheet.ShowSubSum([{
  StdCol: "standardCD",
  CntCol: "standardCD",          // 건수 집계 컬럼
  SumCols: "DMAmt|DLAmt|DEAmt",  // 합계 컬럼
  AvgCols: "DMUP|DLUP|DEUP",     // 평균 컬럼
  Sort: "asc"
}]);
```

### HideSubSum
```javascript
mySheet.HideSubSum();
```

### ShowSubSum 파라미터

| 속성 | 설명 |
|------|------|
| `StdCol` | 기준 컬럼 (SaveName 또는 인덱스) |
| `SumCols` | 합계 대상 컬럼들 (`\|` 구분) |
| `CntCol` | 건수 집계 컬럼 |
| `AvgCols` | 평균 집계 컬럼들 |
| `Sort` | 정렬 (`"asc"`, `"desc"`, 0) |
| `CaptionCol` | 캡션 표시 컬럼 |
| `ShowCumulate` | 누계 표시 |
| `OtherColText` | 기타 컬럼 텍스트 |

---

## 피벗 (Pivot)

### ShowPivotDialog
피벗 다이얼로그를 표시합니다 (단축키: Ctrl+Shift+T).
```javascript
mySheet.ShowPivotDialog();
```

### 피벗 시트 참조
피벗 결과는 `시트ID_Pivot` 이름의 시트로 생성됩니다.
```javascript
if (typeof mySheet_Pivot != "undefined") {
  mySheet_Pivot.Down2Excel({FileName:"pivotSheet.xlsx", SheetDesign:1, Merge:1});
}
```

---

## 예제: 필터

> 출처: `docs/examples/02/filter.html`

```javascript
function LoadPage() {
  var initSheet = {};
  initSheet.Cfg = {SearchMode:smLazyLoad, Page:30, HeaderCheckMode:1};
  initSheet.Cols = [
    {Header:"NO", Type:"Seq", Width:40, SaveName:"SEQ", Align:"Center"},
    {Header:"", Type:"CheckBox", Width:40, SaveName:"CHK", Align:"Center"},
    {Header:"차량명", Type:"Text", Width:165, SaveName:"NAME"},
    {Header:"가격", Type:"AutoSum", Width:70, SaveName:"PRICE", Format:"#,###만원", Align:"Center"}
  ];
  IBS_InitSheet(mySheet, initSheet);

  mySheet.ShowFilterRow();
  mySheet.SetCountPosition(2);
}

// 프로그래밍 방식 필터 적용
mySheet.SetFilterValue("CHK", 1, 1);

// 필터된 데이터만 엑셀 다운
mySheet.Down2Excel({FileName:"FilteredData.xlsx", SheetName:"필터된 데이터",
  DownRows:"Visible", SheetDesign:1});
```

## 예제: 그룹

> 출처: `docs/examples/03/group.html`

```javascript
function LoadPage() {
  var initSheet = {};
  initSheet.Cfg = {SearchMode:smLazyLoad, UseGroupActionMenu:1};
  initSheet.Cols = [
    {Header:"용량", Type:"AutoSum", SaveName:"qty", MinWidth:80, GroupSumType:"Sum"},
    {Header:"전체용량", Type:"AutoSum", SaveName:"pkgqty", MinWidth:80, GroupSumType:"Sum"}
  ];
  IBS_InitSheet(mySheet, initSheet);
  mySheet.SetCountPosition(4);

  mySheet.ShowGroupRow("", "{%s} <font color='red'>(<b>{%c}</b>건)</font>");
}
```

## 예제: 피벗

> 출처: `docs/examples/03/pivot.html`

```javascript
function LoadPage() {
  var initData = {};
  initData.Cfg = {SearchMode:smLazyLoad, MergeSheet:msHeaderOnly};
  initData.Cols = [
    {Header:"행/열 필드|부서명", Type:"Text", SaveName:"sDept", Width:80, Align:"Center", Edit:0},
    {Header:"값 필드|급여", Type:"Int", SaveName:"sSalary", MinWidth:80, Format:"#,###  원"}
  ];
  IBS_InitSheet(mySheet, initData);

  mySheet.SetCellBackColor(0, 0, "#006c62");
  mySheet.SetCellFontColor(0, 0, "#FFFFFF");
}

// 피벗 다이얼로그 표시
mySheet.ShowPivotDialog();

// 피벗 시트 엑셀 다운로드
if (typeof mySheet_Pivot != "undefined") {
  mySheet_Pivot.Down2Excel({FileName:"pivotSheet.xlsx", SheetDesign:1, Merge:1});
}
```

## 예제: 그룹/필터 토글

> 출처: `docs/examples/100/variousFunc.html`

```javascript
// 그룹핑
case "group":
  if (mySheet.Rows.GroupRow && mySheet.Rows.GroupRow.Visible) {
    mySheet.HideGroupRow();
  } else {
    mySheet.HideFilterRow();
    mySheet.ShowGroupRow("", "{%s} <font color='red'>(<b>{%c}</b>건)</font>");
  }
  break;

// 필터링
case "filter":
  if (mySheet.FindFilterRow() > 0) {
    mySheet.HideFilterRow();
  } else {
    mySheet.HideGroupRow();
    mySheet.ShowFilterRow();
  }
  break;
```
