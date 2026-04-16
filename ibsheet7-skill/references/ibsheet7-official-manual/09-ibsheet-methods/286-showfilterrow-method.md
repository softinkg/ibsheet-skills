# ShowFilterRow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ShowFilterRow Method

---

- **기능**

> IBSheet 상단 고정행으로 필터행을 추가한다.
>
> 이 함수를 사용하면 컬럼별 데이터에 대한 필터링 기능을 사용할 수 있다.
>
> 함수의 호출 시점은 초기화 이후 조회 처리전에 호출 하여야 한다.

- **Syntax**

|        |                           |
|:------:|---------------------------|
| Syntax | ObjId.**ShowFilterRow**() |

- **Info**

> **Return**: None

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```
//필터행 추가하기
mySheet.ShowFilterRow();
```

- **제공 버전**

7.0.0.0