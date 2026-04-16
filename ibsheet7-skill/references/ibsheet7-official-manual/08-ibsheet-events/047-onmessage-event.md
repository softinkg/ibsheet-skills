# OnMessage Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnMessage Event

---

- **기능**

> SetShowMsgMode(0)인 경우 각종 확인 메시지 또는 경고 메시지가 발생했을 때 시스템 팝업이 표시되는 것이 아니라 이 이벤트가 발생한다. 확인 메시지인 경우는 IsConfirm = 1이므로, 반드시 ConfirmOK 함수를 이용하여 응답 결과를 Sheet로 되돌려 준다.

- **Syntax**

|        |                                                              |
|:------:|--------------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnMessage**(Msg, Level, IsConfirm) { } |

- **Parameters**

| Parameter | Type    | 설 명                                                                                                     |
| --------- | ------- | ------------------------------------------------------------------------------------------------------- |
| Msg       | String  | 메시지                                                                                                     |
| Level     | String  | 메시지 레벨 코드 "U" – EndUser를 위한 메시지 "E" – 개발자를 위한 메시지 "D" – 서버 연결 함수의 페이지 관련 메시지 "X" – 조회, 저장XML의 XML파서 메시지 |
| IsConfirm | Boolean | 확인 메시지 여부                                                                                               |

- **Example**

```javascript
//메시지 모드를 설정한다.
mySheet.SetShowMsgMode(0);
//OnMessage 이벤트를 처리한다.
Function mySheet_OnMessage(Msg, Level, IsConfirm) {
//메시지 표시하기
var win_result = window.showModalDialog(
"sheet_message.jsp?Msg=" + Msg + "&IsConfirm=" + IsConfirm,
‘modalResult',
‘dialogWidth:200px;dialogHeight:200px;center:yes;help:no;status:no;');
//Sheet로 메시지 결과를 반환한다.
If(IsConfirm) mySheet.ConfirmOK(win_result);
}
```

- **제공 버전**

7.0.0.0