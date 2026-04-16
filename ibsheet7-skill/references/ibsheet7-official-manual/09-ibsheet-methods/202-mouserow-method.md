# MouseRow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > MouseRow Method

---

- **기능**

> 마우스가 눌려졌을 때 선택된 행 번호를 반환한다. 데이터 영역이 아닌 경우는 –1을 반환한다.

- **Syntax**

|        |                      |
|:------:|----------------------|
| Syntax | ObjId.**MouseRow**() |

- **Info**

> **Return**: Long, 마우스포인터가 있는 셀의 행 Index

| Parameter | Type | 설 명 |
| --------- | ---- | --- |
| 없음        |      |     |

- **Example**

```javascript
//마우스가 눌러졌을 때 행 번호를 가져온다.
Function mySheet_OnMouseDown(Button, Shift, X, Y){
//눌린 행 확인
alert(mySheet.MouseRow() + "행이 눌림");
}
```

- **제공 버전**

7.0.0.0