# 고급 기능

## CalcLogic (컬럼 자동 계산)

### 문자열 수식
`|컬럼SaveName|` 으로 다른 컬럼 값을 참조합니다.
```javascript
{Type:"AutoSum", SaveName:"TOTAL", CalcLogic:"|QTY|*|PRICE|"}
{Type:"AutoSum", SaveName:"DIFF", CalcLogic:"|A|-|B|"}
{Type:"AutoSum", SaveName:"ROUNDED", CalcLogic:"ROUNDDOWN(|A|+0.5678,3)"}
```

### 함수형 수식
복잡한 계산 로직은 함수형으로 작성합니다.
```javascript
{Type:"AutoSum", SaveName:"CALC", CalcLogic:{
  TriggerCol:"COL1|COL2",   // 트리거 컬럼 (이 컬럼 값 변경 시 재계산)
  Function: function(calInfo) {
    var v1 = calInfo.Sheet.GetCellValue(calInfo.Row, "COL1");
    var v2 = calInfo.Sheet.GetCellValue(calInfo.Row, "COL2");
    return v1 * v2;
  }
}}
```

### CalcLogic에서 사용자 함수
```javascript
// 사용자 정의 함수
function ROUNDDOWN(n, num_digits) {
  var p = Math.pow(10, num_digits);
  return (Math.trunc(n * p)) / p;
}

// CalcLogic에서 사용
{CalcLogic:"ROUNDDOWN(|A|+0.5678999,3)"}
```

---

## Drag & Drop

### 설정
```javascript
initData.Cfg = {
  DragMode: 1,     // 드래그 모드 활성화
  DragCell: 1       // 셀 단위 드래그
};
```

### 이벤트
```javascript
function mySheet_OnCellDropEnd(Obj, Row, Col, ToObj, ToRow, ToCol) {
  var bValue = ToObj.GetCellValue(ToRow, ToCol);
  var aValue = Obj.GetCellValue(Row, Col);

  if (ToRow < 0) return;

  if (ToObj && ToRow > 0 && ToCol >= 0) {
    ToObj.SetCellValue(ToRow, ToCol, aValue);
    Obj.SetCellValue(Row, Col, bValue || "");
  }
}
```

---

## Undo/Redo

### 설정
```javascript
initSheet.Cfg = {Undo: 1};
// Ctrl+Z: Undo, Ctrl+Y: Redo
```

---

## 찾기 다이얼로그

### ShowFindDialog / SetFindDialog
```javascript
mySheet.SetFindDialog({FirstStart: 0, KeepDialog: 1});
mySheet.ShowFindDialog();
```

### FindText
텍스트 검색을 수행합니다.
```javascript
mySheet.FindText(col, text, startRow, matchMode);
```

### FindCheckedRow
체크된 행을 찾습니다.
```javascript
var rows = mySheet.FindCheckedRow("SaveName", {ReturnArray: 1});
```

---

## 간트차트

Html 타입 컬럼을 활용하여 간트 바를 생성합니다.

### 설정
```javascript
init_data.Cfg = {FrozenCol:2, MergeSheet:msHeaderOnly, AutoFitColWidth:""};
init_data.Cols = [
  {Header:"프로젝트명|프로젝트명", Type:"Text", Width:150, SaveName:"cls", TreeCol:1},
  {Header:"PM|PM", Type:"Text", Width:60, SaveName:"pm", Align:"Center"},
  {Header:"시작일|시작일", Type:"Date", Width:100, SaveName:"sdate", Format:"yyyy-MM-dd"},
  {Header:"완료일|완료일", Type:"Date", Width:100, SaveName:"edate", Format:"yyyy-MM-dd"},
  {Header:"경과율|경과율", Type:"Int", Width:80, SaveName:"percent", Format:"#,##0\\%"},
  // 간트 영역 (Html 타입으로 그래프 렌더링)
  {Header:"2024|1분기", Type:"Html", Width:80, SaveName:"gantt"},
  {Header:"2024|2분기", Type:"Html", Width:80, SaveName:""},
  {Header:"2024|3분기", Type:"Html", Width:80, SaveName:""},
  {Header:"2024|4분기", Type:"Html", Width:80, SaveName:""}
];
```

---

## 관계형 콤보 (대분류/중분류)

Combo 컬럼 간 연관 데이터를 설정합니다.
```javascript
var param = {
  sheet: mySheet,
  comboCols: "SIDO|SIGUNGU",
  data: combodata  // 계층적 JSON 구조
};
setMultiCombo(param);
```

---

## 입력 키 제어

```javascript
{Header:"계약번호", Type:"Text", SaveName:"CONTRACTNO", AcceptKeys:"N|E"} // 숫자+영문만
{Header:"차량번호", Type:"Text", SaveName:"CARNO", ExceptKeys:"E"}         // 영문 제외
```

---

## 예제: 함수형 CalcLogic (고급 계산)

> 출처: `docs/examples/100/calclogic.html`

```javascript
// 매출 계산 (요금 x 일수)
var SALEAMTCAL = {
  TriggerCol: "RENTFEE|RENTDATE|RETURNDATE",
  Function: function(calInfo) {
    var RENTFEE = calInfo.Sheet.GetCellValue(calInfo.Row, "RENTFEE");
    var SD = calInfo.Sheet.GetCellText(calInfo.Row, "RENTDATE").split("/");
    var ED = calInfo.Sheet.GetCellText(calInfo.Row, "RETURNDATE").split("/");
    var day = (new Date(ED[0], ~~ED[1]-1, ED[2]) - new Date(SD[0], ~~SD[1]-1, SD[2])) / 86400000;
    return RENTFEE * day;
  }
};

// 순매출 (총매출의 90%)
var NETSALEAMTCAL = {
  TriggerCol: "SALEAMTCAL",
  Function: function(calInfo) {
    return (calInfo.Sheet.GetCellValue(calInfo.Row, "SALEAMT") / 100) * 90;
  }
};

initSheet.Cols = [
  {Header:"24시간기본요금", Type:"Float", SaveName:"RENTFEE", Format:"#,###.##"},
  {Header:"출고일자", Type:"Date", SaveName:"RENTDATE", Format:"Ymd"},
  {Header:"입고일자", Type:"Date", SaveName:"RETURNDATE", Format:"Ymd"},
  {Header:"순매출", Type:"AutoSum", SaveName:"NETSALEAMT", Format:"#,##0", CalcLogic:NETSALEAMTCAL},
  {Header:"총매출", Type:"AutoSum", SaveName:"SALEAMT", Format:"#,##0", CalcLogic:SALEAMTCAL}
];
```

## 예제: Drag & Drop

> 출처: `docs/examples/14_DataMove/cell_move.html`

```javascript
function LoadPage() {
  var initData = {};
  initData.Cfg = {
    SearchMode: 2,
    Page: 50,
    MergeSheet: msHeaderOnly,
    DragMode: 1,
    DragCell: 1
  };
  initData.Cols = [
    {Header:"", Type:"Seq", Width:35, Align:"Center"},
    {Header:"사원", Type:"Html", SaveName:"col1", Width:80},
    {Header:"주임", Type:"Html", SaveName:"col2", Width:80},
    {Header:"대리", Type:"Html", SaveName:"col3", Width:80}
  ];
  IBS_InitSheet(mySheet, initData);
  mySheet.SetDataRowHeight(104);
}

function mySheet_OnCellDropEnd(Obj, Row, Col, ToObj, ToRow, ToCol) {
  var bValue = ToObj.GetCellValue(ToRow, ToCol);
  var aValue = Obj.GetCellValue(Row, Col);

  if (ToRow < 0) return;

  if (ToObj && ToRow > 0 && ToCol >= 0) {
    ToObj.SetCellValue(ToRow, ToCol, aValue);
    Obj.SetCellValue(Row, Col, bValue || "");
  }
}
```

## 예제: 간트차트

> 출처: `docs/examples/12/gantt.html`

```javascript
function LoadPage() {
  var init_data = {};
  init_data.Cfg = {FrozenCol:2, MergeSheet:msHeaderOnly, AutoFitColWidth:""};
  init_data.Cols = [
    {Header:"프로젝트명|프로젝트명", Type:"Text", Width:150, SaveName:"cls", TreeCol:1},
    {Header:"PM|PM", Type:"Text", Width:60, SaveName:"pm", Align:"Center"},
    {Header:"시작일|시작일", Type:"Date", Width:100, SaveName:"sdate", Format:"yyyy-MM-dd"},
    {Header:"완료일|완료일", Type:"Date", Width:100, SaveName:"edate", Format:"yyyy-MM-dd"},
    {Header:"경과율|경과율", Type:"Int", Width:80, SaveName:"percent", Format:"#,##0\\%"},
    {Header:"2024|1분기", Type:"Html", Width:80, SaveName:"gantt"},
    {Header:"2024|2분기", Type:"Html", Width:80, SaveName:""},
    {Header:"2024|3분기", Type:"Html", Width:80, SaveName:""},
    {Header:"2024|4분기", Type:"Html", Width:80, SaveName:""}
  ];
  init_data.HeaderMode = {Sort:1, ColMove:0, ColResize:0};
  IBS_InitSheet(mySheet, init_data);
  mySheet.SetCountPosition(3);
}

// OnLoadData에서 간트 바 HTML 생성
function mySheet_OnLoadData(data) {
  var obj = JSON.parse(data);
  var jdata = obj["Data"];
  for (var i = 0; i < jdata.length; i++) {
    drawGantt(jdata[i]);
  }
  return obj;
}

function drawGantt(item) {
  var wposRate = /* 시작 위치 퍼센트 계산 */;
  var eposRate = /* 기간 퍼센트 계산 */;
  var rate = item["percent"];

  item["gantt"] = "<div style='width:100%;height:30px'>" +
    "<div class='ganttBarMain' style='left:" + wposRate + "%;width:" + eposRate +
    "%;background-color:#4d9dff'>" +
    "<div style='background-color:#fea176;height:100%;width:" + rate + "%'></div>" +
    "</div></div>";
}

// 간트 바 영역 셀 병합
function mySheet_OnSearchEnd(code, msg) {
  var mergeArr = [];
  for (var i = mySheet.GetDataFirstRow(); i <= mySheet.GetDataLastRow(); i++) {
    mergeArr.push([i, 5, 1, 8]);
  }
  mySheet.SetMergeCell(mergeArr, true);
}

// 값 변경 시 간트 바 재그리기
function mySheet_OnChange(row, col, v, ov) {
  var rowData = mySheet.GetRowData(row);
  drawGantt(rowData);
  mySheet.SetRowData(row, rowData);
}
```

## 예제: 관계형 콤보

> 출처: `docs/examples/04/combo.html`

```javascript
var combodata = [
  {"01":"경북", "ITEM":[
    {"01":"울진군"}, {"02":"김천시"}, {"03":"영양군"}
  ]},
  {"02":"대구", "ITEM":[
    {"01":"동구"}, {"02":"달서구"}, {"03":"북구"}
  ]}
];

function LoadPage() {
  var cols = [
    {Type:"Combo", Width:100, SaveName:"SIDO"},
    {Type:"Combo", Width:100, SaveName:"SIGUNGU"}
  ];
  mySheet.SetConfig({SearchMode:smLazyLoad, Page:50});
  mySheet.InitHeaders(headers, {Sort:1, ColMove:1, ColResize:1});
  mySheet.InitColumns(cols);

  setMultiCombo({
    sheet: mySheet,
    comboCols: "SIDO|SIGUNGU",
    data: combodata
  });
}
```
