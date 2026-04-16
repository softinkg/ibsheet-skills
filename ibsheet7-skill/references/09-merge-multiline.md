# 셀 병합 / 멀티라인

## 자동 머지 (MergeSheet)

### MergeSheet 설정
```javascript
initSheet.Cfg = {MergeSheet: msHeaderOnly};
```

### 머지 유형 동적 변경
```javascript
mySheet.SetMergeSheet(msNone);          // 머지 없음
mySheet.SetMergeSheet(msHeaderOnly);    // 헤더만
mySheet.SetMergeSheet(1);               // 전체 머지
mySheet.SetMergeSheet(7);               // 앞 컬럼 기준 (msPrevColumnMerge)
```

> **참고**: 머지 모드 변경 후 재조회가 필요합니다.

### ColMerge 속성
컬럼별로 행 방향 머지를 개별 제어합니다.
```javascript
{Header:"신청인", Type:"Text", SaveName:"Person", ColMerge:1}   // 머지 적용
{Header:"금액", Type:"AutoSum", SaveName:"AMT", ColMerge:0}     // 머지 미적용
```

### PrevColumnMerge 모드
앞 컬럼의 값이 같을 때만 현재 컬럼을 머지합니다.
```javascript
initSheet.Cfg = {MergeSheet: msPrevColumnMerge};
// 또는
initSheet.Cfg = {MergeSheet: 7, PrevColumnMergeMode: 1};
```

### 데이터 머지 재적용
```javascript
mySheet.SetDataMerge();
```

---

## 수동 머지 (SetMergeCell)

### 단일 영역 병합
```javascript
mySheet.SetMergeCell(row, col, rowSpan, colSpan);
```

### 다중 영역 병합 (배열)
```javascript
mySheet.SetMergeCell([
  [row1, col1, rowSpan1, colSpan1],
  [row2, col2, rowSpan2, colSpan2]
], true);
```

---

## 멀티헤더

Header 문자열에 `|` 구분자를 사용하여 2단 이상 헤더를 생성합니다.

### 2단 헤더
```javascript
{Header:"근태기간|시작일", Type:"Date", SaveName:"START"}
{Header:"근태기간|종료일", Type:"Date", SaveName:"END"}
// "근태기간" 부분이 자동으로 병합되어 2단 헤더 생성
```

### 3단 헤더
```javascript
{Header:"변경예정(도급)|재료비|단가", Type:"Int", SaveName:"DMUP"}
{Header:"변경예정(도급)|재료비|금액", Type:"AutoSum", SaveName:"DMAmt"}
```

### 헤더 줄바꿈
```javascript
{Header:"체결\n조건", Type:"Text", SaveName:"param5"}  // \n으로 줄바꿈
```

---

## 멀티라인 레코드

하나의 레코드를 여러 행으로 표시합니다. Cols를 2차원 배열로 구성합니다.

### 필수 설정
```javascript
initSheet.Cfg = {MergeSheet: msFixedMerge + msHeaderOnly};
```

### Cols 2차원 배열 구성
```javascript
initSheet.Cols = [
  [ // 첫번째 데이터 행
    {Header:"상태", Type:"Status", SaveName:"sStatus", RowSpan:2},
    {Header:"종류", Type:"Text", SaveName:"category"},
    {Header:"가격", Type:"AutoSum", SaveName:"price", RowSpan:2}
  ],
  [ // 두번째 데이터 행
    {Header:"상태"},    // RowSpan으로 첫번째 행에 병합됨
    {Header:"제품명", Type:"Text", SaveName:"productName"},
    {Header:"가격"}     // RowSpan으로 첫번째 행에 병합됨
  ]
];
```

- `RowSpan`: 해당 컬럼이 차지하는 행 수
- 병합된 셀은 `Header`만 지정 (Type, SaveName 생략)

---

## 예제: 머지 모드별 설정

> 출처: `docs/examples/05/merge.html`

```javascript
function LoadPage() {
  var initdata = {};
  initdata.Cfg = {SearchMode:smLazyLoad, MergeSheet:msHeaderOnly};
  initdata.Cols = [
    {Header:"No|No", Type:"Seq", Width:80},
    {Header:"신청인|신청인", Type:"Text", Width:80, ColMerge:1, SaveName:"Person"},
    {Header:"근태기간|시작일", Type:"Date", Width:100, Format:"Ymd", ColMerge:0, SaveName:"WorkStart"},
    {Header:"근태기간|종료일", Type:"Date", Width:100, Format:"Ymd", ColMerge:0, SaveName:"WorkEnd"},
    {Header:"시간|시작", Type:"Date", Width:100, Format:"Hm", ColMerge:1, SaveName:"WorkStartT"},
    {Header:"시간|종료", Type:"Date", Width:100, Format:"Hm", ColMerge:1, SaveName:"WorkEndT"}
  ];
  IBS_InitSheet(mySheet, initdata);
}

// 머지 모드 동적 변경 (변경 후 재조회 필요)
mySheet.SetMergeSheet(msNone);          // 머지 없음
mySheet.SetMergeSheet(msHeaderOnly);    // 헤더만
mySheet.SetMergeSheet(1);               // 전체 머지
mySheet.SetMergeSheet(7);               // 앞 컬럼 기준 머지
doAction('search');
```

## 예제: 멀티라인 레코드

> 출처: `docs/examples/01/multiline.html`

```javascript
function LoadPage() {
  mySheet.ThemeVersion = 1;
  mySheet.SetTheme("GY2", "Gray2");

  var ibsheet = {};
  ibsheet.Cfg = {SearchMode:smLazyLoad, MergeSheet: msFixedMerge + msHeaderOnly};
  ibsheet.Cols = [
    [ // 첫번째 데이터 행
      {Header:"상태", Type:"Status", SaveName:"sStatus", RowSpan:2},
      {Header:"선택", Type:"CheckBox", SaveName:"CHK"},
      {Header:"이미지", Type:"Image", SaveName:"productImage", RowSpan:2, ImgWidth:60, ImgHeight:60},
      {Header:"종류", Type:"Text", SaveName:"category"},
      {Header:"특징", Type:"Text", SaveName:"spec", RowSpan:2, Wrap:1, MultiLineText:1},
      {Header:"가격", Type:"AutoSum", SaveName:"price", RowSpan:2},
      {Header:"혜택", Type:"Html", SaveName:"benefit"},
      {Header:"등록일", Type:"Text", SaveName:"cdate", Format:"Ymd"}
    ],
    [ // 두번째 데이터 행
      {Header:"상태"},
      {Header:"순번", Type:"Seq", SaveName:"SEQ"},
      {Header:"이미지"},
      {Header:"제품명", Type:"Text", SaveName:"productName", FontUnderline:1},
      {Header:"특징"},
      {Header:"가격"},
      {Header:"배송비", Type:"AutoSum", SaveName:"shipping"},
      {Header:"판매자", Type:"Image", SaveName:"seller", ImgHeight:22}
    ]
  ];
  IBS_InitSheet(mySheet, ibsheet);

  mySheet.SetEditableColorDiff(0);
  mySheet.SetEditArrowBehavior(0);
  mySheet.SetClickHeaderMapping(1);
}

// 합계행 커스터마이징
function mySheet_OnSearchEnd(code, msg) {
  mySheet.SetCellValue(mySheet.LastRow() - 1, 0, "합 계");
  mySheet.SetMergeCell(mySheet.LastRow() - 1, 0, 2, 4);
}
```
