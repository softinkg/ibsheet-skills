# ShowMsgMode Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ShowMsgMode Method

---

- **기능**

> Sheet에서 발생하는 각종 메시지를 시스템 팝업 형태로 사용할것인지 이벤트 방식을 사용할것인지 설정한다.
>
> 이 속성이 1이면 모든 메시지는 시스템 팝업으로 발생하고, 이 속성이 0이면 OnMessage Event가 발생한다. 메시지 표시창에 디자인을 적용해야 한다거나, 버튼의 개수를 변경해야 할때 이 속성을 0으로 설정하고, OnMessage Event, ConfirmOK Method를 함께 사용한다.

- **Syntax**

|        |     |                            |
|:------:|:---:|----------------------------|
| Syntax | Get | ObjId.**GetShowMsgMode**() |

- **Info**

> **Return**: Boolean, 현재 설정 값(Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//메시지 모드를 확인한다.
mySheet.GetShowMsgMode();
```

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Set | ObjId.**SetShowMsgMode**(Mode) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명       |
| --------- | ------- | ---- | --------- |
| Mode      | Boolean | 필수   | 메시지 표시 여부 |

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
If(IsConfirm) mySheet.ConfirmOK( win_result);
}
```

- **제공 버전**

> **7.0.0.0**
>
> **  **