# OnBeforePaste Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnBeforePaste Event

---

- **기능**

> 시트에 데이터를 붙여넣기 직전에 발생한다

- **Syntax**

|        |                                                 |
|:------:|-------------------------------------------------|
| Syntax | **function 오브젝트ID_OnBeforePaste**(text) { } |

- **Parameters**

|           |        |                        |
|:---------:|:------:|:----------------------:|
| Parameter |  Type  |         설 명          |
|   text    | String | 시트에 붙여넣을 텍스트 |

- **Remarks**

> 데이터를 붙여넣기 전에 발생하며 필요에 따라 붙여넣기를 취소하거나 붙여넣을 값을 수정 할 수 있다. False 리턴시 붙여넣기는 취소되며, 문자열 리턴시 붙여넣을 텍스트가 대체된다.

- **Example**

```javascript
function mySheet_OnBeforePaste(text) {
if(text == "not allow text") {
alert("붙여넣기가 최소됩니다.");
return false;
}
}
function mySheet_OnBeforePaste(text) {
if(text == "not allow text") {
return "allow text";
}
}
```

- **제공 버전**

7.0.0.0