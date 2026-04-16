# OnBeforeEdit Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnBeforeEdit Event

---

- **기능**

> 셀의 값을 편집하기 직전에 이벤트가 발생한다.

- **Syntax**

|        |                                                    |
|:------:|----------------------------------------------------|
| Syntax | **function 오브젝트ID_OnBeforeEdit**(Row, Col) { } |

- **Parameters**

|           |      |                        |
|:---------:|:----:|:----------------------:|
| Parameter | Type |         설 명          |
|    Row    | Long |  해당 셀의 Row Index   |
|    Col    | Long | 해당 셀의 Column Index |

- **Example**

```javascript
//컬럼이 이동된 후 이벤트가 발생한다.
Function mySheet_OnBeforeEdit(Row, Col) {
alert("입력을 시작합니다.");
}
```

- **제공 버전**

7.0.0.0