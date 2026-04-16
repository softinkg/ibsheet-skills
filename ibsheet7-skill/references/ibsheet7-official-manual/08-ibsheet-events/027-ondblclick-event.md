# OnDblClick Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnDblClick Event

---

- **기능**

> 데이터 영역의 셀을 마우스로 더블 클릭했을 때 이벤트가 발생한다.

- **Syntax**

|  |  |
|:--:|----|
| Syntax | **function 오브젝트ID_OnDblClick**(Row, Col, Value, CellX, CellY, CellW, CellH) { } |

- **Parameters**

|           |        |                        |
|:---------:|:------:|:----------------------:|
| Parameter |  Type  |         설 명          |
|    Row    |  Long  |  해당 셀의 Row Index   |
|    Col    |  Long  | 해당 셀의 Column Index |
|   Value   | String |    해당 셀의 Value     |
|   CellX   |  Long  |     해당셀의 X좌표     |
|   CellY   |  Long  |     해당셀의 Y좌표     |
|   CellW   |  Long  |  해당셀의 가로 넓이값  |
|   CellH   |  Long  |  해당셀의 세로 높이값  |

- **Example**

```javascript
function mySheet_OnDblClick(Row, Col, Value, CellX, CellY, CellW, CellH) {
//더블 클릭했을 때, 선택행의 값을 전달 어미 창으로 전달.
var selectRowJson = mySheet.GetRowData(Row);
parent.GetData(selectRowJson);
self.close();
return false; //창을 닫는 경우에는 false를 리턴해 줘야 함.
}
```

- **제공 버전**

7.0.0.0