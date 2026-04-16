# OnBeforeExpand Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnBeforeExpand Event

---

- **기능**

> 트리 형태일 때 클릭시 트리가 펼쳐지기 전 또는 접히기 전에 이벤트가 발생한다.

- **Syntax**

|        |                                                         |
|:------:|---------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnBeforeExpand**(Row, Expand) { } |

- **Parameters**

| Parameter | Type   | 설 명                 |
| --------- | ------ | ------------------- |
| Row       | Number | 해당 셀의 Row Index     |
| Expand    | Number | 0 : 펼치는 경우 2 : 접는경우 |

- **Example**

```javascript
function mySheet_OnBeforeExpand(Row, Expand) {
if(Row == 1 && Expand == 2) {
mySheet.SetAllowExpand(0);
alert("1 행에서는 펼칠 수 있지만 접을 수 없습니다.");
}
}
```

- **제공 버전**

7.0.0.0