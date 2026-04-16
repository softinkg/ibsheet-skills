# OnClick Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnClick Event

---

- **기능**

> 데이터 영역의 셀을 마우스로 클릭했을 때 이벤트가 발생한다.

- **Syntax**

|  |  |
|:--:|----|
| Syntax | **function 오브젝트ID_OnClick**(Row, Col, Value, CellX, CellY, CellW, CellH, rowType) { } |

- **Parameters**

|  |  |  |
|:--:|:--:|:--:|
| Parameter | Type | 설 명 |
| Row | Long | 해당 셀의 Row Index |
| Col | Long | 해당 셀의 Column Index |
| Value | String | 이벤트가 발생한 셀의 값 |
| CellX | Long | 해당셀의 X좌표 |
| CellY | Long | 해당셀의 Y좌표 |
| CellW | Long | 해당셀의 가로 넓이값 |
| CellH | Long | 해당셀의 세로 높이값 |
| rowType | String | 해당 Row의 타입(HeaderRow, SubSumRow, SumRow, DataRow, CumulateRow) |

- **Example**

```javascript
function mySheet_OnClick(Row, Col, Value, CellX, CellY, CellW, CellH) {
//특정 열을 클릭했을 때 다른 페이지로 이동하도록 처리
if( mySheet.ColSaveName(Col) == "LINK_BUFF"){
location.href = "link.jsp?key=" + mySheet.GetCellValue(Row,"KFELD");
}
}
```

- **제공 버전**

7.0.0.0

>