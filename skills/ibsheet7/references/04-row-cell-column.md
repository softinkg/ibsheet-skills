# 행/셀/컬럼 조작

## 행 조작

### 행 추가/삭제
```javascript
var row = mySheet.DataInsert();              // 마지막에 추가
var row = mySheet.DataInsert(targetRow);     // 특정 행 위치에 추가

mySheet.RowDelete(row);     // 행 삭제 (실제 삭제는 저장 시)
mySheet.RemoveAll();         // 전체 데이터 삭제
mySheet.Reset();             // 시트 초기화 (구조 포함)
```

### 행 정보 조회
```javascript
mySheet.RowCount();           // 행 수
mySheet.GetDataFirstRow();    // 데이터 첫번째 행
mySheet.GetDataLastRow();     // 데이터 마지막 행
mySheet.LastRow();            // 합계행
mySheet.HeaderRows();         // 헤더 행 수
```

### 행 선택/포커스
```javascript
mySheet.GetSelectRow();       // 선택된 행
mySheet.GetSelectCol();       // 선택된 열
mySheet.MouseRow();           // 마우스 위치 행
mySheet.MouseCol();           // 마우스 위치 열

mySheet.SelectCell(row, col, {Edit: false});  // 특정 셀로 포커스 이동
mySheet.SetSelectRow(row);                    // 특정 행으로 포커스 이동
```

### 행 데이터
```javascript
mySheet.GetRowData(row);              // 행 데이터 가져오기
mySheet.SetRowData(row, rowData);     // 행 데이터 설정

mySheet.GetSelectionRows();           // 선택 영역 행 ("1|2|3" 형태)
```

### 행 숨김/표시
```javascript
mySheet.SetRowHidden(row, 1);  // 숨김
mySheet.SetRowHidden(row, 0);  // 표시
```

### 행 편집 제어
```javascript
mySheet.SetRowEditable(row, 1);  // 편집 가능
mySheet.SetRowEditable(row, 0);  // 편집 불가
```

### 행 스타일
```javascript
mySheet.SetRowBackColor(row, "#FF0000");  // 행 배경색
mySheet.SetDataRowHeight(40);              // 행 높이 설정
```

### 행 이동
```javascript
mySheet.DataMove(0, row);  // 데이터 이동
```

---

## 셀 조작

### 셀 값 읽기/쓰기
```javascript
mySheet.GetCellValue(row, col);       // 실제 값
mySheet.GetCellText(row, "SaveName"); // 표시 텍스트

mySheet.SetCellValue(row, col, value);      // 셀 값 설정
mySheet.SetCellValue(row, col, value, 0);   // 이벤트 미발생
```

### 셀 속성
```javascript
mySheet.GetCellProperty(row, col, "Type");  // 셀 속성 읽기
mySheet.GetCellEditable(row, col);          // 편집 가능 여부
```

### 셀 스타일
```javascript
mySheet.SetCellBackColor(row, col, "#FF0000");  // 배경색
mySheet.SetCellBackColor(row, col, "");          // 색상 초기화
mySheet.SetCellFontColor(row, col, "#0000FF");   // 글자색
mySheet.SetCellAlign(row, col, "Center");        // 정렬
```

### 셀 병합
```javascript
mySheet.SetMergeCell(row, col, rowSpan, colSpan);           // 단일 병합
mySheet.SetMergeCell(mergeArray, true);                      // 배열로 여러 영역 병합
```

---

## 컬럼 조작

### 컬럼 숨김/표시
```javascript
mySheet.SetColHidden(col, 1);  // 숨김
mySheet.SetColHidden(col, 0);  // 표시
mySheet.GetColHidden(col);     // 숨김 여부

// 초기화 시 숨김
{Header:"시도", Type:"Text", SaveName:"SIDO", Hidden:1}
```

### 컬럼 스타일/편집
```javascript
mySheet.SetColBackColor(col, "#EEEEEE");  // 컬럼 배경색
mySheet.SetColEditable(col, 1);            // 편집 가능
mySheet.SetColEditable(col, 0);            // 편집 불가
```

### 컬럼 속성 설정
```javascript
mySheet.SetColProperty(row, "SaveName", {ComboText:"A|B", ComboCode:"1|2"});
```

### 컬럼 인덱스 변환
```javascript
mySheet.ColSaveName(0, colIndex);   // Index → SaveName
mySheet.SaveNameCol("SaveName");    // SaveName → Index
mySheet.LastCol();                   // 마지막 컬럼 인덱스
```

### 컬럼 너비 조정
```javascript
mySheet.FitColWidth();

// 자동 컬럼 너비 (초기화 시)
initSheet.Cfg = {AutoFitColWidth: "init|search|resize"};
```

---

## 행/열 고정 (Frozen)

```javascript
// 행 고정
mySheet.SetFrozenRows(rowIndex);

// 열 고정 (초기화 시)
initSheet.Cfg = {FrozenCol: 3};

// 동적 열 고정
mySheet.SetFrozenCol(colIndex);
```

---

## 예제: 행/열/셀 편집 제어

> 출처: `docs/examples/04/edit.html`

```javascript
// 행 편집 가능/불가능
mySheet.SetRowEditable(row, 1);  // 가능
mySheet.SetRowEditable(row, 0);  // 불가능

// 열 편집 가능/불가능
mySheet.SetColEditable(col, 1);
mySheet.SetColEditable(col, 0);

// UpdateEdit:0 → 수정행(R상태)은 편집 불가
{Header:"코드", Type:"Text", SaveName:"CODE", UpdateEdit:0}
```

## 예제: 행/열 고정

> 출처: `docs/examples/04/frozen.html`

```javascript
// 행 고정
mySheet.SetFrozenRows(rowIndex);

// 열 고정 (초기화 시)
initSheet.Cfg = {FrozenCol: 3};

// 동적 열 고정
mySheet.SetFrozenCol(colIndex);

// 고정 행/열 배경색 설정
for (var i = 1; i <= rowIdx; i++) {
  mySheet.SetRowBackColor(i, "#EEEEEE");
}
```

## 예제: 행/열 숨김

> 출처: `docs/examples/04/hidden.html`

```javascript
// 행 숨김/표시
mySheet.SetRowHidden(row, 1);
mySheet.SetRowHidden(row, 0);

// 열 숨김/표시
mySheet.SetColHidden(col, 1);
mySheet.SetColHidden(col, 0);

// 초기화 시 숨김
{Header:"시도", Type:"Text", SaveName:"SIDO", Hidden:1}

// 자동 컬럼 너비 조정
initSheet.Cfg = {AutoFitColWidth: "init|search|resize"};
```
