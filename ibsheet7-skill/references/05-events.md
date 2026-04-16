# 이벤트 핸들러

## 이벤트 명명 규칙

이벤트 함수명은 반드시 `시트ID_이벤트명` 규칙을 따릅니다.
```javascript
// 시트ID가 mySheet인 경우
function mySheet_OnSearchEnd(code, msg, StCode, StMsg) { }

// 시트ID가 sheet2인 경우
function sheet2_OnClick(row, col) { }
```

---

## 조회/저장 이벤트

### OnSearchEnd
조회 완료 시 호출됩니다.
```javascript
function mySheet_OnSearchEnd(code, msg, StCode, StMsg) {
  // code < 0: 오류
}
```

### OnSaveEnd
저장 완료 시 호출됩니다.
```javascript
function mySheet_OnSaveEnd(code, msg) {
  // code < 0: 오류
  if (msg != "") alert(msg);
}
```

### OnLoadData
데이터 로드 시 호출됩니다. 데이터 가공이 가능합니다.
```javascript
function mySheet_OnLoadData(data) {
  var obj = JSON.parse(data);
  // 데이터 가공...
  return obj;
}
```

---

## 마우스 이벤트

### OnClick / OnDblClick
```javascript
function mySheet_OnClick(row, col, cellx, celly, cellw, cellh) {
  if (row == null || row < 0) return;
}

function mySheet_OnDblClick(row, col, cellx, celly, cellw, cellh) {
  if (row == null || row < 0) return;
}
```

### OnMouseDown / OnMouseUp / OnMouseMove
```javascript
function mySheet_OnMouseDown(button, shift, x, y) {}
function mySheet_OnMouseUp(button, shift, x, y) {}
function mySheet_OnMouseMove(button, shift, x, y) {}
```

---

## 버튼/팝업 이벤트

### OnButtonClick
Button 타입 컬럼 클릭 시 호출됩니다.
```javascript
function mySheet_OnButtonClick(Row, Col) {
  alert(Row + "행의 버튼이 클릭되었습니다.");
}
```

### OnPopupClick
Popup/PopupEdit 타입 컬럼의 팝업 버튼 클릭 시 호출됩니다.
```javascript
function mySheet_OnPopupClick(Row, Col) {
  var v = mySheet.GetCellText(Row, "ISO");
  document.getElementById("popupFrame").src = "./popup.jsp?searchCondition=" + encodeURIComponent(v);
}
```

---

## 키보드 이벤트

### OnKeyDown / OnKeyUp
```javascript
function mySheet_OnKeyDown(row, col, key, shift) {}
function mySheet_OnKeyUp(row, col, key, shift) {}
```

---

## 셀/행 이벤트

### OnSelectCell
포커스 이동 시 호출됩니다.
```javascript
function mySheet_OnSelectCell(oldrow, oldcol, row, col, isDelete) {}
```

### OnChange
값 변경 시 호출됩니다.
```javascript
function mySheet_OnChange(row, col, value, oldvalue) {
  if (row == null || row < 0) return;
}
```

### OnAfterEdit
편집 완료 시 호출됩니다.
```javascript
function mySheet_OnAfterEdit(row, col) {
  var val = mySheet.GetCellValue(row, col);
}
```

### OnSort
정렬 시 호출됩니다.
```javascript
function mySheet_OnSort(col, arrow) {}
```

---

## 트리 이벤트

### OnBeforeExpand / OnAfterExpand
트리 노드 접기/펼치기 시 호출됩니다.
```javascript
function mySheet_OnBeforeExpand(row, expand) {}
function mySheet_OnAfterExpand(row, expand) {}
```

---

## 컬럼 이벤트

### OnUserResize
컬럼 크기 변경 시 호출됩니다.
```javascript
function mySheet_OnUserResize(col, width) {}
```

### OnBeforeColumnMove / OnAfterColumnMove
컬럼 이동 시 호출됩니다.
```javascript
function mySheet_OnBeforeColumnMove(Col, NewPos) {}
function mySheet_OnAfterColumnMove(Col, NewPos) {}
```

---

## 필터/그룹 이벤트

### OnFilterEnd
필터 적용 완료 시 호출됩니다.
```javascript
function mySheet_OnFilterEnd(RowCnt, FirstRow) {}
```

### OnGroupFinish
그룹화 완료 시 호출됩니다.
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

## 기타 이벤트

### OnBeforePaste
붙여넣기 전 호출됩니다.
```javascript
function mySheet_OnBeforePaste(txt) {}
```

### OnSelectMenu
우클릭 메뉴 선택 시 호출됩니다.
```javascript
function mySheet_OnSelectMenu(text, code) {
  if (text == "엑셀 파일 저장") {
    mySheet.Down2Excel({FileName:"movieList.xlsx", SheetName:"movieList", SheetDesign:1});
  }
}
```

### OnCellDropEnd
Drag & Drop 완료 시 호출됩니다.
```javascript
function mySheet_OnCellDropEnd(Obj, Row, Col, ToObj, ToRow, ToCol) {}
```

### OnLoadExcel
엑셀 업로드 완료 시 호출됩니다.
```javascript
function mySheet_OnLoadExcel(result) {}
```

---

## 예제: 종합 이벤트 처리

> 출처: `docs/examples/09/event.html`

```javascript
function mySheet_OnSearchEnd(code, msg, StCode, StMsg) {
  console.log("[OnSearchEnd] Code:" + code + ", Message:" + msg);
}

function mySheet_OnSaveEnd(code, msg) {
  console.log("[OnSaveEnd] Code:" + code + ", Message:" + msg);
}

function mySheet_OnClick(row, col, cellx, celly, cellw, cellh) {
  if (row == null || row < 0) return;
  console.log("[OnClick] Row:" + row + ", Col:" + col);
}

function mySheet_OnDblClick(row, col) {
  if (row == null || row < 0) return;
}

function mySheet_OnSelectCell(oldrow, oldcol, row, col, isDelete) {
  console.log("[OnSelectCell] " + oldrow + "," + oldcol + " -> " + row + "," + col);
}

function mySheet_OnChange(row, col, value, oldvalue) {
  if (row == null || row < 0) return;
  console.log("[OnChange] " + row + "," + col + " => " + value + " (이전:" + oldvalue + ")");
}

function mySheet_OnAfterEdit(row, col) {
  var val = mySheet.GetCellValue(row, col);
  console.log("[OnAfterEdit] " + row + ":" + col + " = " + val);
}

function mySheet_OnSort(col, arrow) {
  console.log("[OnSort] Col:" + col + ", Arrow:" + arrow);
}

function mySheet_OnKeyDown(row, col, key, shift) {
  console.log("[OnKeyDown] Key:" + key + ", Shift:" + shift);
}

function mySheet_OnMouseDown(button, shift, x, y) {
  console.log("[OnMouseDown] Button:" + button);
}

function mySheet_OnAfterColumnMove(Col, NewPos) {
  console.log("[OnAfterColumnMove] " + Col + " => " + NewPos);
}

function mySheet_OnUserResize(col, width) {
  console.log("[OnUserResize] Col:" + col + ", Width:" + width);
}

function mySheet_OnBeforeExpand(row, expand) {}
function mySheet_OnAfterExpand(row, expand) {}

function mySheet_OnFilterEnd(RowCnt, FirstRow) {
  console.log("[OnFilterEnd] RowCnt:" + RowCnt + ", FirstRow:" + FirstRow);
}
```
