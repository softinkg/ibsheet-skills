# ReturnData Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ReturnData Method

---

- **기능**

> 특정 행의 데이터를 조회 상태의 문자열로 변경한다.
>
> 조회된 데이터로 되돌리지 못하는 경우는 다음과 같다
>
> 1\. 조회된 데이터가 아닌 경우, 예를 들면 입력 상태의 데이터
>
> 2\. 상태컬럼이 존재하지 않는 경우

- **Syntax**

|        |                           |
|:------:|---------------------------|
| Syntax | ObjId.**ReturnData**(Row) |

- **Info**

> **Return**: None

| Parameter | Type | 필수여부 | 설 명              |
| --------- | ---- | ---- | ---------------- |
| Row       | Long | 필수   | 데이터 행의 Row Index |

- **Example**

```
//초기 상태로 변경하기
mySheet.ReturnData(2);
```

- **제공 버전**

7.0.0.0