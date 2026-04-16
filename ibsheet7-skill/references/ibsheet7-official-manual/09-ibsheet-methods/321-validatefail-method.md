# ValidateFail Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ValidateFail Method

---

- **기능**

> 저장 함수를 호출하여 저장 처리 전에 저장할 각 데이터의 Validation 확인을 위한 OnValidation 이벤트에서 유효하지 않은 데이터를 발견하여 저장처리를 중단하고자 할 때 이 속성을 설정하여 처리를 중단한다.
>
> OnEditValidation 이벤트에서 사용하는 경우 Fail 인자의 설정에 따라 다음과 같이 처리 할 수 있다. Fail 설정 값이 2 이고 Message 인자를 설정한 경우 Message 인자에 설정한 값을 메시지로 표시 한다.

|              |                                              |
|:------------:|:--------------------------------------------:|
| Fail 설정 값 |                     설명                     |
|      1       | Invalid 처리 (입력값 취소 / 편집 완료 처리)  |
|      2       | Invalid 처리 (입력값의 상태로 편집상태 유지) |

- **Syntax**

|        |                                           |
|:------:|-------------------------------------------|
| Syntax | ObjId.**ValidateFail**(Fail, [Message]) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                       |
| --------- | ------ | ---- | ------------------------- |
| Fail      | Number | 필수   | 저장 처리 중단 여부               |
| Message   | String | 선택   | Fail 인자 설정이 2인 경우 표시할 메시지 |

- **Example**

```javascript
// OnValidation 이벤트에서의 사용
function mySheet_OnValidation(Row, Col, Value) {
if(Col == 2) {
if(Value=="원화" && mySheet.GetCellValue(Row,Col+1) >= 10000000) {
alert("통화가 원화일 때 금액은 천만원 이상일수없습니다. ");
mySheet.ValidateFail(1);
mySheet.SelectCell(Row, Col+1);
} else if(Value=="외화" && mySheet.GetCellValue(Row,Col+1) < 10000000) {
alert("통화가 외화일 때 금액은 천만원 이상이여야 합니다. ");
mySheet.ValidateFail(1);
mySheet.SelectCell(Row, Col+1);
}
}
}
// OnEditValidation 이벤트에서의 사용
function mySheet_OnEditValidation(Row, Col, Value) {
if(Col == 2 && Value > 100) {
// alert 으로 메시지를 표시하고 편집상태를 유지한다.
mySheet.ValidateFail(2, "금액 최대값은 100입니다");
}
}
```

- **제공 버전**

| **7.0.0.0** |                                               |
|:-----------:|-----------------------------------------------|
| **7.0.1.0** | Fail시 편집 유지 모드 추가, Message 인자 추가 |