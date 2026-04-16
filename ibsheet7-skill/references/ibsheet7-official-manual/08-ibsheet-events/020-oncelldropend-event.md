# OnCellDropEnd Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnCellDropEnd Event

---

- **기능**

> 셀 단위 Drag를 시작 후 Drop 시점에 이벤트가 발생한다.

- **Syntax**

|  |  |
|:--:|----|
| Syntax | **function 오브젝트ID_OnCellDropEnd**(FromSheet, FromRow, FromCol, ToSheet, ToRow, ToCol, X, Y) { } |

- **Parameters**

|           |        |                                     |
|:---------:|:------:|:-----------------------------------:|
| Parameter |  Type  |                설 명                |
| FromSheet | Object |        Drag 위치 Sheet 객체         |
|  FromRow  |  Long  |  Drag 위치 Sheet 객체의 Row Index   |
|  FromCol  |  Long  | Drag 위치 Sheet 객체의 Column Index |
|  ToSheet  | Object |        Drop 위치 Sheet 객체         |
|   ToRow   |  Long  |  Drop 위치 Sheet 객체의 Row Index   |
|   ToCol   |  Long  | Drop 위치 Sheet 객체의 Column Index |
|     X     |  Long  |         Drop 위치의 X 좌표          |
|     Y     |  Long  |         Drop 위치의 Y 좌표          |

- **Example**

```javascript
// 드래그 셀의 Value를 드랍위치 셀에 설정한다
function mySheet_OnCellDropEnd(FromSheet, FromRow, FromCol, ToSheet, ToRow, ToCol) {
var bValue = ToObj.GetCellValue(ToRow, ToCol);
var aValue = Obj.GetCellValue(Row, Col);
if (ToRow < 0) {
ToRow = ToObj.DataInsert(ToRow);
ToCol = ToObj.MouseCol();
}
if (ToObj && ToRow > 0 && ToCol >= 0) {
ToObj.SetCellValue(ToRow, ToCol, aValue);
if (bValue) {
Obj.SetCellValue(Row, Col, bValue);
} else {
Obj.SetCellValue(Row, Col, "");
}
}
}
```

- **제공 버전**

7.0.0.0