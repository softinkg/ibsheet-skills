# GetEditText Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetEditText Method

---

- **기능**

> Edit 중인 글자를 확인한다.

- **Syntax**

|        |                         |
|:------:|-------------------------|
| Syntax | ObjId.**GetEditText**() |

- **Info**

> **Return**: String, 편집중인 글자 (Default="")

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없읍        |      |      |     |

- **Example**

```javascript
// 편집중인 글자를 확인한다.
Function mySheet_OnKeyUp(Row, Col, KeyCode, Shift){
var editTxt= "Edit중인 글자 = " + mySheet.GetEditText();
editTxt += "실제글자 = " + mySheet.GetCellValue(Row,Col);
alert(editTxt);
}
```

- **제공 버전**

> **7.0.0.0**
>
> **  **