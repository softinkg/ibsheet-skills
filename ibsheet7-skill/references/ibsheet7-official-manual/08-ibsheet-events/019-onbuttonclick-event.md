# OnButtonClick Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnButtonClick Event

---

- **기능**

> "Button" 컬럼타입의 버튼 클릭시 발생하는 이벤트
>
> 해당 셀의 Editable이 false인 경우에는 이벤트가 발생하지 않는다

- **Syntax**

|        |                                                     |
|:------:|-----------------------------------------------------|
| Syntax | **function 오브젝트ID_OnButtonClick**(Row, Col) { } |

- **Parameters**

|           |        |                   |
|:---------:|:------:|:-----------------:|
| Parameter |  Type  |       설 명       |
|    Row    | Number |  대상 행의 Index  |
|    Col    | Number | 대상 컬럼의 Index |

- **Example**

```javascript
function mySheet_OnButtonClick(Row, Col) {
console.log("[" + Row + "," + Col + "] 셀의 버튼 클릭");
}
```

- **제공 버전**

| **7.0.13.9** |     |
|--------------|-----|