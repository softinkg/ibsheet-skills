# 엑셀/PDF/인쇄

## 엑셀 다운로드 (Down2Excel)

### Down2Excel(params)
```javascript
var params = {
  FileName: "myFile.xlsx",
  SheetName: "MYWORKSHEET",
  SheetDesign: 1,           // 디자인 반영
  Merge: 1,                 // 머지 반영
  DownCols: "3|4|5|6",      // 다운로드할 컬럼 (생략 시 전체)
  DownRows: "Visible",      // 보이는 행만
  DownSum: 1,               // 합계행 포함
  TitleText: "제목\r\n\r\n", // 상단 타이틀
  UserMerge: "0,0,2,8",     // 타이틀 영역 병합 (row,col,rowCnt,colCnt)
  ComboValidation: 1,       // 엑셀 내 콤보 유효성
  HiddenColumn: 1,          // 숨긴 컬럼 포함
  CheckBoxOnValue: "Y",
  CheckBoxOffValue: "N",
  ExcelRowHeight: 20,
  KeyFieldMark: 0,
  WordWrap: false,
  AutoSizeColumn: 1,        // 컬럼 자동 너비
  UseFormula: 1              // 수식 사용
};
mySheet.Down2Excel(params);
```

### Down2Excel 전체 파라미터

| 파라미터 | 설명 | 기본값 |
|----------|------|--------|
| `FileName` | 파일명 | |
| `SheetName` | 워크시트명 | |
| `SheetDesign` | 디자인 반영 | 0 |
| `Merge` | 머지 반영 | 0 |
| `DownCols` | 다운로드 컬럼 (`\|` 구분) | 전체 |
| `DownRows` | 다운로드 행 (`"Visible"`) | 전체 |
| `DownSum` | 합계행 포함 | 0 |
| `TitleText` | 상단 타이틀 | |
| `UserMerge` | 타이틀 병합 영역 | |
| `ComboValidation` | 콤보 유효성 | 0 |
| `HiddenColumn` | 숨긴 컬럼 포함 | 0 |
| `CheckBoxOnValue` | 체크박스 참값 | |
| `CheckBoxOffValue` | 체크박스 거짓값 | |
| `ExcelRowHeight` | 행 높이 | |
| `KeyFieldMark` | 필수필드 표시 | 1 |
| `WordWrap` | 줄바꿈 | true |
| `AutoSizeColumn` | 컬럼 자동 너비 | 0 |
| `UseFormula` | 수식 사용 | 0 |

### SetDown2ExcelConfig
엑셀 다운로드 기본 설정을 변경합니다.
```javascript
mySheet.SetDown2ExcelConfig({ExcelRowHeight:"18", AutoSizeColumn:1, ExcelFontSize:"10"});
```

### ExportMode
```javascript
mySheet.ExportMode = 1;  // 서버
mySheet.ExportMode = 2;  // 클라이언트
```

---

## 엑셀 업로드 (LoadExcel)

### LoadExcel(params)
```javascript
var params = {
  Mode: "HeaderMatch",       // 매칭 방식
  FileExt: "xls|xlsx|xltx"  // 허용 확장자
};
mySheet.LoadExcel(params);
```

### Mode 옵션
| 값 | 설명 |
|-----|------|
| `"HeaderMatch"` | 헤더 비교하여 매칭 |
| `"NoHeader"` | 순서대로 매칭 |
| `"HeaderSkip"` | 첫행 무시 |

### 엑셀 업로드 이벤트
```javascript
function mySheet_OnLoadExcel(result) {}
```

---

## 다중 시트 엑셀 (버퍼)

### 다운로드
```javascript
mySheet.Down2ExcelBuffer(true);
mySheet.Down2Excel({SheetName:"Sheet1", SheetDesign:1});
mySheet2.Down2Excel({SheetName:"Sheet2", SheetDesign:1});
mySheet.Down2ExcelBuffer(false);
```

### 업로드
```javascript
mySheet.LoadExcelBuffer(true);
mySheet.LoadExcel({Mode:"HeaderMatch", WorkSheetName:"Sheet1"});
mySheet2.LoadExcel({Mode:"HeaderMatch", WorkSheetName:"Sheet2"});
mySheet.LoadExcelBuffer(false);
```

---

## 대용량 엑셀 (DirectDown2Excel)

서버에서 직접 엑셀을 생성합니다.
```javascript
var params = {
  URL: "directdown2excel_data.jsp",
  FileName: "대용량.xlsx",
  SheetName: "sheet-test",
  Merge: 1,
  SheetDesign: 1,
  HiddenColumn: 1,
  ExtendParam: "serviceID=8937&emp_id=SA9082"
};
mySheet.DirectDown2Excel(params);
```

---

## PDF 다운로드

### Down2Pdf(params)
```javascript
var params = {
  FileName: "myFile",
  Paper: "landscape",      // portrait | landscape
  Title: "IB Sheet PDF",
  TitleStyle: "color:red;size:12pt;",
  DPI: 1400
};
mySheet.Down2Pdf(params);
```

---

## 인쇄

### DoPrint()
```javascript
mySheet.DoPrint();
```

---

## 예제: 엑셀 다운로드 (고급)

> 출처: `docs/examples/11/excel.html`

```javascript
case "down2excel":
  var DandT = new Date().toLocaleString();
  var downCols = makeHiddenSkipCol(mySheet);

  var TITLE = "[잔업 수당 신청]\r\n\r\n|문서번호:  (0009)";
  TITLE += "\r\n | 신청기간: 2003-09 ~ 2004-09";
  TITLE += "\r\n[ " + mySheet.RowCount() + " ]건, 출력시간 : " + DandT + "||||||단위: 원";

  var userMG = "0,0,2,8 2,1,1,5 3,1,1,5 4,0,1,5 4,6,1,2";

  var params = {
    FileName: "myFile.xlsx",
    SheetName: "MYWORKSHEET",
    Merge: 1,
    DownCols: downCols,
    SheetDesign: 1,
    TitleText: TITLE,
    UserMerge: userMG,
    DownSum: 1,
    ComboValidation: 1,
    CheckBoxOnValue: "Y",
    CheckBoxOffValue: "N",
    ExcelRowHeight: 20,
    KeyFieldMark: 0,
    WordWrap: 0,
    AutoSizeColumn: 1
  };
  mySheet.Down2Excel(params);
  break;
```

### 숨김 컬럼 제외 헬퍼
```javascript
function makeHiddenSkipCol(sobj) {
  var lc = sobj.LastCol();
  var colsArr = [];
  for (var i = 0; i <= lc; i++) {
    var coltype = sobj.GetCellProperty(0, i, "Type");
    if (sobj.GetColHidden(i) == 0 &&
        coltype != "Seq" && coltype != "Status" && coltype != "DelCheck") {
      colsArr.push(i);
    }
  }
  return colsArr.join("|");
}
```

## 예제: 엑셀 타이틀 포함 다운로드

> 출처: `docs/examples/01/datatype.html`

```javascript
case "Down2Excel":
  var param = {
    FileName: "DataType_test.xlsx",
    SheetDesign: 1,
    TitleText: "데이터 타입/포멧 예제\r\n\r\n",
    UserMerge: "0,0,2,12",
    ComboValidation: 1,
    WordWrap: false
  };
  mySheet.Down2Excel(param);
  break;
```

## 예제: 다중 시트 엑셀

> 출처: `docs/examples/08/multisave.html`

```javascript
// 다중 시트 엑셀 다운로드
case "exceldown":
  mySheet.Down2ExcelBuffer(true);
  mySheet.Down2Excel({SheetName:"가족 정보", SheetDesign:1});
  mySheet2.Down2Excel({SheetName:"거래량 통계", SheetDesign:1});
  mySheet.Down2ExcelBuffer(false);
  break;

// 다중 시트 엑셀 업로드
case "excelup":
  mySheet.LoadExcelBuffer(true);
  mySheet.LoadExcel({Mode:"HeaderMatch", WorkSheetName:"가족 정보", StartRow:5});
  mySheet2.LoadExcel({Mode:"HeaderMatch", WorkSheetName:"거래량 통계", StartRow:5});
  mySheet.LoadExcelBuffer(false);
  break;
```

## 예제: 대용량 엑셀 + 서버 페이징

> 출처: `docs/examples/13_search/serverpaging.html`

```javascript
mySheet.SetDown2ExcelConfig({ExcelRowHeight:"18", AutoSizeColumn:1, ExcelFontSize:"10"});
mySheet.DirectDown2Excel({
  URL: "directdown2excel_data.jsp",
  FileName: "대용량.xlsx",
  SheetName: "sheet-test",
  Merge: 1,
  SheetDesign: 1,
  HiddenColumn: 1,
  ExtendParam: "serviceID=8937&emp_id=SA9082"
});
```

## 예제: PDF 다운로드

> 출처: `docs/examples/11/pdf.html`

```javascript
case "down2pdf":
  var params = {
    FileName: "UsedCarData",
    Paper: "landscape",
    Title: "IB Sheet PDF File",
    TitleStyle: "color:red;size:12pt;",
    DPI: document.body.clientWidth * 2 - 200
  };
  mySheet.Down2Pdf(params);
  break;
```
