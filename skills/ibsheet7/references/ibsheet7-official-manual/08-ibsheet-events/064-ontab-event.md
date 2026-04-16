# OnTab Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnTab Event

---

- **기능**

시트에서 탭 키를 누르는 경우 OnTab 이벤트가 발생한다.

**isLast** 인자의 경우 탭으로 이동할 수 있는 마지막 셀인경우 반환되는 값으로 Shift + Tab을 누르는 경우 첫셀, Tab을 누르는 경우 마지막 셀에서 1값을 반환한다.

TabBehavior, EditTabBehavior를 설정한 경우 설정값에 따라서 이동할 수 있는 마지막 셀에서 1값이 반환된다.

(이전행/컬럼과 현재행/컬럼이 동일한 경우에 1로 반환됨)

- **Syntax**

|  |  |
|:--:|----|
| Syntax | **function 오브젝트ID_OnTab**(Row, Col, Old_Row, Old_Col, isShift, isLast) { } |

- **Parameters**

|           |         |                    |
|:---------:|:-------:|:------------------:|
| Parameter |  Type   |       설 명        |
|    Row    |  Long   |  선택된 행 인덱스  |
|    Col    |  Long   | 선택된 컬럼 인덱스 |
|  Old_Row  |  Long   |   이전 행 인덱스   |
|  Old_Col  |  Long   |  이전 컬럼 인덱스  |
|  isShift  | Boolean | Shift 키 입력 여부 |
|  isLast   | Boolean |   마지막 셀 여부   |

- **Example**

```javascript
function mySheet_OnTab(Row, Col, Orow, Ocol, isShift, isLast) {
alert("[OnTab] New : " + Row + "," + Col + " Old : " + Orow + "," + Ocol + " Shift : " + isShift + " isLast : " + isLast);
}
```

- **제공 버전**

7.0.0.0

>