# 데이터 조회/저장

## 조회 메서드

### DoSearch(url)
서버에서 직접 조회합니다 (가장 일반적).
```javascript
mySheet.DoSearch("url.json");
```

### GetSearchData(url) + LoadSearchData(data)
서버에서 데이터만 가져온 후 별도 로드합니다.
```javascript
var jsonStr = mySheet.GetSearchData("url.json");
mySheet.LoadSearchData(jsonData);
```

### DoSearchPaging(url, params)
서버 페이징 조회입니다 (대량 데이터).
```javascript
mySheet.DoSearchPaging("url.jsp", {Param:"onepagerow=100"});
```

> **주의**: `SearchMode:smServerPaging2`일 때는 반드시 `DoSearchPaging()` 사용

---

## 저장 메서드

### DoSave(url)
변경된 데이터만 서버로 전송합니다.
```javascript
mySheet.DoSave("saveUrl.jsp");
```

### DoAllSave(url)
전체 데이터를 서버로 전송합니다.
```javascript
mySheet.DoAllSave("saveUrl.jsp");
```

### GetSaveString(allFlag)
변경 데이터를 QueryString으로 추출합니다.
```javascript
var saveStr = mySheet.GetSaveString();    // 변경분
var saveStr = mySheet.GetSaveString(1);   // 전체
```

### GetSaveJson(options)
변경 데이터를 JSON으로 추출합니다.
```javascript
var saveJson = mySheet.GetSaveJson();
var saveJson = mySheet.GetSaveJson({AllTypeToText: 1}); // 모든 값을 문자열로
```

### GetSaveData(url, paramString)
서버에 저장하고 결과를 받습니다.
```javascript
var rtnData = mySheet.GetSaveData("saveUrl.jsp", paramString);
```

### LoadSaveData(response)
저장 결과를 시트에 반영합니다 (서버 응답으로 상태 갱신).
```javascript
mySheet.LoadSaveData({Result:{Code:1, Message:"저장되었습니다."}});
```

---

## 데이터 형식

### 조회 데이터 형식 (JSON)
```json
{
  "Data": [
    {"NAME":"홍길동", "AMT":10000, "STATUS":"R"},
    {"NAME":"김철수", "AMT":20000, "STATUS":"R"}
  ]
}
```

### 저장 응답 형식 (JSON)
```json
{
  "Result": {
    "Code": 1,
    "Message": "저장되었습니다."
  }
}
```
- `Code >= 0`: 성공 (시트 상태 초기화, I/U/D → R)
- `Code < 0`: 실패 (시트 상태 유지)

### EtcData (추가 데이터)
조회 응답에 시트 외 데이터를 포함할 수 있습니다.
```javascript
// 조회 응답 JSON에 포함
{"Data":[...], "EtcData":{"SawonNo":"12345","Name":"홍길동"}}

// 사용
var etcJson = mySheet.EtcData;
mySheet.GetEtcData("SawonNo");
```

---

## 예제: 기본 CRUD

> 출처: `docs/examples/01/transaction.html`

```javascript
function doAction(sAction) {
  switch(sAction) {
    case "search":
      mySheet.DoSearch("transaction_data.json");
      break;
    case "reload":
      mySheet.RemoveAll();
      break;
    case "save":
      var tempStr = mySheet.GetSaveString();
      alert("서버로 전달되는 문자열: " + tempStr);
      break;
    case "save2":
      alert("저장 JSON: " + JSON.stringify(mySheet.GetSaveJson()));
      break;
    case "insert":
      var row = mySheet.DataInsert();
      break;
  }
}
```

## 예제: GetSearchData + LoadSearchData

> 출처: `docs/examples/01/datatype.html`

```javascript
case "search":
  var json = mySheet.GetSearchData("datatype_data.json");
  mySheet.LoadSearchData(json);
  break;
```

## 예제: 저장 서버 응답 처리

> 출처: `docs/examples/08/save.html`

```javascript
// 변경된 행만 저장
mySheet.DoSave("save.jsp");

// 전체 행 저장
mySheet.DoAllSave("save.jsp");

// 저장 완료 이벤트
function mySheet_OnSaveEnd(code, msg) {
  if (msg != "") {
    alert(msg);
  }
}
```

## 예제: 서버 페이징

> 출처: `docs/examples/13_search/serverpaging.html`

```javascript
function LoadPage() {
  createIBSheet2(document.getElementById("ibSheet"), "mySheet", "100%", "100%");
  mySheet.Reset();

  var initdata = {};
  initdata.Cfg = {
    SearchMode: smServerPaging2,  // 서버 페이징 모드
    Page: 100,
    MergeSheet: msNone,
    DeferredVScroll: 1,
    PagingPosition: 1
  };
  initdata.Cols = [
    {Header:"No", Type:"Text", Width:80, SaveName:"RN", Align:"center", ColMerge:0},
    {Header:"선택", Type:"CheckBox", Width:75, SaveName:"CHK", ColMerge:0},
    {Header:"우편번호", Type:"Text", Width:85, SaveName:"POSTNO", Format:"PostNo", ColMerge:0},
    {Header:"주소", Type:"Text", Width:300, SaveName:"ADDRESS"}
  ];
  IBS_InitSheet(mySheet, initdata);

  mySheet.SetEditableColorDiff(2);
  mySheet.SetScrollInfoFormat("데이터 로딩 중...");
  mySheet.SetEditable(1);
  mySheet.SetCountPosition(4);
}

// 서버 페이징 조회 (반드시 DoSearchPaging 사용!)
mySheet.DoSearchPaging("serverpaging_data.jsp", {
  Param: "onepagerow=100"
});
```

## 예제: 다중 시트 조회/저장

> 출처: `docs/examples/08/multisave.html`

```javascript
// 다중 시트 조회 (하나의 응답에서 분리)
var jsonStr = mySheet.GetSearchData("./multisave_data.json");
var A = JSON.parse(jsonStr);
mySheet.LoadSearchData(A.sheet1);
mySheet2.LoadSearchData(A.sheet2);

// 다중 시트 저장
var param1 = mySheet.GetSaveString();
var param2 = mySheet2.GetSaveString();
if (param1 == "" && param2 == "") {
  alert("저장할 데이터가 없습니다");
  return;
}
var rtnData = mySheet.GetSaveData("save.jsp", param1 + "&" + param2);
mySheet.LoadSaveData(rtnData);
mySheet2.LoadSaveData(rtnData);

// EtcData를 Form에 매핑
function mySheet_OnSearchEnd() {
  var etcJson = mySheet.EtcData;
  IBS_CopyJson2Form({"searchForm": etcJson}, document.searchForm);
}
```
