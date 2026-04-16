# OnAfterEdit Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnAfterEdit Event

---

- **기능**

> 셀의 값을 편집한 직후에 이벤트가 발생한다.

- **Syntax**

|        |                                                   |
|:------:|---------------------------------------------------|
| Syntax | **function 오브젝트ID_OnAfterEdit**(Row, Col) { } |

- **Parameters**

|           |      |                        |
|:---------:|:----:|:----------------------:|
| Parameter | Type |         설 명          |
|    Row    | Long |  해당 셀의 Row Index   |
|    Col    | Long | 해당 셀의 Column Index |

- **Example**

```javascript
//값을 편집한 직후 이벤트가 발생한다.
Function mySheet_OnAfterEdit(Row, Col) {
alert("입력을 마칩니다.");
}
```

- **제공 버전**

7.0.0.0

- **See Also  
  [OnBeforeEdit](#onbeforeedit-event)**