# OnDropEnd Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnDropEnd Event

---

- **기능**

> 행 단위 Drag를 시작 후 Drop 시점에 이벤트가 발생한다.
>
> 이벤트 인자중 Type 인자는 트리구조에서 Drop 위치의 상세 값을 전달 한다.
>
> Type 인자의 값은 아래와 같다

| Type | 설명                |
|:----:|---------------------|
|  1   | Drop 위치 행의 상단 |
|  2   | Drop 위치 행의 중앙 |
|  3   | Drop 위치 행의 하단 |

- **Syntax**

|  |  |
|:--:|----|
| Syntax | **function 오브젝트ID_OnDropEnd**(FromSheet, FromRow, ToSheet, ToRow, X, Y, Type) { } |

- **Parameters**

|           |         |                                   |
|:---------:|:-------:|:---------------------------------:|
| Parameter |  Type   |               설 명               |
| FromSheet | Object  |       Drag 위치 Sheet 객체        |
|    Row    |  Long   | Drag 위치 Sheet 객체의 Row Index  |
|  ToSheet  | Object  |       Drop 위치 Sheet 객체        |
|   ToRow   |  Long   | Drop 위치 Sheet 객체의 Row Index  |
|     X     | Integer |        Drop 위치의 X 좌표         |
|     Y     | Integer |        Drop 위치의 Y 좌표         |
|   Type    | Integer | 트리 구조인 경우 Drop 위치의 타입 |

- **Example**

```javascript
// 드래그 행을 드랍위치에 추가하고 드래그 시트에서 삭제한다.
Function mySheet_OnDropEnd(FromSheet, FromRow, ToSheet, ToRow, X, Y, Type) {
var NewRow = ToObj.DataInsert(ToRow);
for (var c = 0; c <= Obj.LastCol(); c++) {
ToObj.SetCellValue(NewRow, c, Obj.GetCellValue(Row, c));
}
Obj.RowDelete(Row);
}
```

- **제공 버전**

7.0.0.0