# OnAfterExpand Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnAfterExpand Event

---

- **기능**

> 트리 형태 시트를 사용할 때 + 기호나 – 기호를 클릭하여 트리를 접거나 펼친후에 이 이벤트가 발생한다.

- **Syntax**

|        |                                                         |
|:------:|---------------------------------------------------------|
| Syntax | **function 오브젝트ID_**OnAfterExpand(Row, Expand) { } |

- **Parameters**

| Parameter | Type | 설 명               |
| --------- | ---- | ----------------- |
| Row       | Long | 해당 셀의 Row Index   |
| Expand    | Long | : 펼치는 경우 2 : 접는경우 |

- **Example**

```javascript
function mySheet_OnAfterExpand(Row, Expand) {
alert( Row + "행, "+ Expand +"의 상태");
}
```

- **제공 버전**

7.0.0.0

- **See Also  
  [OnBeforeExpand](#onbeforeexpand-event), [RowExpand](#rowexpanded-method), [RowLevel](#rowlevel-method), [ShowTreeLevel](#showtreelevel-method)**