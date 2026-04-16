# ConfirmOK Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ConfirmOK Method

---

- **기능**

> OnMessage Event에서 IsConfirm = 1인 경우 확인창을 표시하고 응답 결과를 Sheet로 되돌려 준다.
>
> ShowMsgMode(0)이면 Sheet에서 메시지가 발생할 때 시스템 팝업이 아닌 OnMessage Event가 발생한다. 발생한 메시지의 종류가 확인용 메시지일때, OnMessage Event의 IsConfirm 인자값이 1이 된다.
>
> 경고용 메시지의 경우 메시지 창이 닫히면 완료되지만, 확인용 메시지의 경우 사용자의 응답을 Sheet로 다시 넘겨주어야 한다. 이 속성은 OnMessage Event 안에서만 사용하며, 응답 결과를 Sheet로 돌려준다.

- **Syntax**

|        |                          |
|:------:|--------------------------|
| Syntax | ObjId.**ConfirmOK**(Val) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명         |
| --------- | ------- | ---- | ----------- |
| Val       | Boolean | 필수   | 확인창 선택 결과 값 |

- **Example**

```javascript
//메시지 모드를 설정한다.
mySheet.ShowMsgMode=0;
//OnMessage 이벤트를 처리한다.
Function mySheet_OnMessage(grid,msg, level, isconfirm)
//메시지 표시하기
var win_result = window.showModalDialog(
"sheet_message.jsp?Msg=" + msg + "&IsConfirm=" + isconfirm,
‘modalResult',
‘dialogWidth:200px;dialogHeight:200px;center:yes;help:no;status:no;');
//Sheet로 메시지 결과를 반환한다.
If(IsConfirm) mySheet.ConfirmOK(win_result);
</script>
```

- **제공 버전**

> **7.0.0.0**