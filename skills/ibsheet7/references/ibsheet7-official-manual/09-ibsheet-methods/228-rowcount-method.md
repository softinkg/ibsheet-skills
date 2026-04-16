# RowCount Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowCount Method

---

- **기능**

> 전체 데이터 행 개수를 확인한다.
>
> Status 값을 설정하지 않은 경우 조회된 데이터 행 개수와 신규 입력된 행까지 포함한 전체 데이터 행 개수를 확인한다.
>
> Status 값에 따라 조회/입력/수정/삭제 각 상태의 행 개수를 확인 할 수 있다.

- **Syntax**

|        |                                |
|:------:|--------------------------------|
| Syntax | ObjId.**RowCount**([Status]) |

- **Info**

> **Return**: Long, 전체 또는 특정 트랜잭션 상태의 데이터행 개수

| Parameter | Type   | 필수여부 | 설 명                     |
| --------- | ------ | ---- | ----------------------- |
| Status    | String | 선택   | 트랜잭션 코드. Default="전체건수" |

- **Example**

```
alert("전체 건수 는 " + mySheet.RowCount() + " 건입니다. ");
alert("조회 건수 는 " + mySheet.RowCount("R") + " 건입니다. ");
alert("입력 건수 는 " + mySheet.RowCount("I") + " 건입니다. ");
alert("수정 건수 는 " + mySheet.RowCount("U") + " 건입니다. ");
alert("삭제 건수 는 " + mySheet.RowCount("D") + " 건입니다. ");
```

- **제공 버전**

> **7.0.0.0**
>
> **  **