# IsDataModified Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > IsDataModified Method

---

- **기능**

> 데이터 행의 트랜잭션 여부를 확인한다.
>
> 트랜잭션 상태가 "조회" 이외의 데이터가 한건이라도 있으면 1을 반환하고, 없으면 0을 반환한다.

- **Syntax**

|        |                            |
|:------:|----------------------------|
| Syntax | ObjId.**IsDataModified**() |

- **Info**

> **Return**: Boolean, 데이터 행의 트랜잭션 여부

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```
// 트랜잭션이 발생하지 않은 경우 메시지 표시 후 저장 취소 처리
if(!mySheet.IsDataModified()) {
alert("저장할 내역이 없습니다. 저장은 취소합니다.");
// 트랜잭션이 발생한 경우 저장 처리
} else {
mySheet.DoSave("sheet_save.jsp");
}
```

- **제공 버전**

7.0.0.0