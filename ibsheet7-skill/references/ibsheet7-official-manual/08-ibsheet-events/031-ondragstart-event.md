# OnDragStart Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnDragStart Event

---

- **기능**

> 행 또는 셀 단위 Drag를 시작할 때 이벤트가 발생 한다.

- **Syntax**

|        |                                                   |
|:------:|---------------------------------------------------|
| Syntax | **function 오브젝트ID_OnDragStart**(Row, Col) { } |

- **Parameters**

|           |      |                          |
|:---------:|:----:|:------------------------:|
| Parameter | Type |          설 명           |
|    Row    | Long |  Drag 위치의 Row Index   |
|    Col    | Long | Drag 위치의 Column Index |

- **Example**

```javascript
var dragValue = "";
function mySheet_OnDragStart(Row, Col) {
// Drag 시작위치의 CellValue를 저장
dragValue = mySheet.GetCellValue(Row, Col) ;
}
```

- **제공 버전**

7.0.0.0