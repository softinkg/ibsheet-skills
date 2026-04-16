# MouseCol Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > MouseCol Method

---

- **기능**

> 마우스가 눌려졌을 때 선택된 컬럼 번호를 반환한다. 데이터 영역이 아닌 경우는 –1을 반환한다.

- **Syntax**

|        |                      |
|:------:|----------------------|
| Syntax | ObjId.**MouseCol**() |

- **Info**

> **Return**: Long, 마우스위치가 있는 컬럼 인덱스

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```javascript
// 마우스가 눌러졌을 때 컬럼 번호를 가져온다.
Function mySheet_OnMouseDown(Button, Shift, X, Y) {
// 눌린 컬럼 확인
alert(mySheet.MouseRow() + "행 " + mySheet.MouseCol() + "컬럼이 눌림");
}
```

- **제공 버전**

> **7.0.0.0**
>
> **  **