# OnPopupClick Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnPopupClick Event

---

- **기능**

> 셀의 Type이 Popup이거나 PopupButton 을 사용하는 셀인 경우 해당 셀에 포커스가 갔을 때 보이는 팝업 버튼을 마우스로 클릭하거나 Edit하려고 할 때 이벤트가 발생한다.
>
> 사용자는 이 이벤트에서 팝업 호출 로직을 기재하여 팝업 처리하도록 한다.

- **Syntax**

|        |                                                    |
|:------:|----------------------------------------------------|
| Syntax | **function 오브젝트ID_OnPopupClick**(Row, Col) { } |

- **Parameters**

|           |      |                        |
|:---------:|:----:|:----------------------:|
| Parameter | Type |         설 명          |
|    Row    | Long |  해당 셀의 Row Index   |
|    Col    | Long | 해당 셀의 Column Index |

- **Example**

```javascript
function mySheet_OnPopupClick(Row,Col) {
//팝업을 연다.
Window.open("Sheet_Popup.jsp?row="+Row+"&col="+Col, "list",
"scrollbars=no,fullscreen=no,width=250,height=350");
}
```

- **제공 버전**

7.0.0.0