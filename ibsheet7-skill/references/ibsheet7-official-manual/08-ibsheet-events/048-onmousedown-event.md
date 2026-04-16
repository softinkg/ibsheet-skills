# OnMouseDown Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnMouseDown Event

---

- **기능**

> 마우스가 눌려졌을 때 이벤트가 발생한다.
>
> 마우스가 눌린 셀의 위치를 알고자 한다면 MouseRow 와 MouseCol 함수를 이용한다.

- **Syntax**

|        |                                                              |
|:------:|--------------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnMouseDown**(Button, Shift, X, Y) { } |

- **Parameters**

| Parameter | Type    | 설 명                                       |
| --------- | ------- | ----------------------------------------- |
| Button    | Integer | 0 : 왼쪽, 2 : 오른쪽 (마우스버튼 방향)                |
| Shift     | Integer | 1 : Shift키가 눌린 경우 2 : Ctrl키가 눌린 경우 0 : 그외 |
| X         | Long    | X좌표                                       |
| Y         | Long    | Y좌표                                       |

- **Example**

```javascript
function mySheet_OnMouseDown(Button, Shift, X, Y) {
//눌린 컬럼 확인
alert(mySheet.MouseRow() + "행 " + mySheet.MouseCol() + "컬럼이 눌림");
}
```

- **제공 버전**

7.0.0.0