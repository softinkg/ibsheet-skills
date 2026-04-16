# FindSumRow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > FindSumRow Method

---

- **기능**

> 합계행의 인덱스를 확인한다.
>
> 합계행이 2개 이상인 경우 (2개행 이상의 단위데이터행 구조인 경우) 합계행의 인덱스를 구분자 "\|" 로 연결한 문자열을 반환 한다.

- **Syntax**

|        |                        |
|:------:|------------------------|
| Syntax | ObjId.**FindSumRow**() |

- **Info**

> **Return**: String, 합계행의 인덱스 (Default=-1)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```javascript
//합계행의 행 번호를 가져온다.
var sumRow = mySheet.FindSumRow();
```

- **제공 버전**

> **7.0.0.0  **