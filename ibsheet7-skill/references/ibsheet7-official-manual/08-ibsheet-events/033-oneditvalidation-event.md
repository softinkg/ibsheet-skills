# OnEditValidation Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnEditValidation Event

---

- **기능**

> 셀의 편집완료 시점에 수정된 값에 대해 Validation Check할수 있도록 이벤트가 발생한다.
>
> Validation에 맞지 않다면 ValidateFail(1)로 설정하여 셀 편집이전의 값으로 되돌린다.

- **Syntax**

|        |                                                               |
|:------:|---------------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnEditValidation**(Row, Col, Value) { } |

- **Parameters**

|           |         |                                            |
|:---------:|:-------:|:------------------------------------------:|
| Parameter |  Type   |                   설 명                    |
|    Row    |  Long   |            해당 셀의 Row Index             |
|    Col    |  Long   |           해당 셀의 Column Index           |
|   Value   | variant | Format이 적용되지 않은 저장 시 사용되는 값 |

- **Example**

```javascript
function mySheet_OnEditValidation(Row, Col, Value) {
if(mySheet.ColSaveName(Col)=="ITMS_CD"){
if(Value.indexOf("현행_")>-1){
alert("현행 정보값은 4/4분기 이후에 설정 가능합니다.");
//값을 이전 값으로 되돌림
mySheet.ValidateFail(1);
}
}
}
```

- **제공 버전**

7.0.0.0