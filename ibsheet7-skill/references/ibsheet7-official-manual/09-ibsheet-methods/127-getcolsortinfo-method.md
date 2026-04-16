# GetColSortInfo Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetColSortInfo Method

---

- **기능**

> 현재 적용되어 있는 컬럼별 Sort 정보를 확인 한다.
>
> 반환되는 값는 Sort 적용 순서로 아래와 같은 형식의 객체에 대한 배열 집합 이다.

| Property  | Type          | 설 명                                |
| --------- | ------------- | ---------------------------------- |
| Col       | Number/String | 컬럼의 Index (단위데이터행 구조인 경우 SaveName) |
| SortOrder | String        | 해당 컬럼의 정렬 방식 ("asc","desc")        |

- **Syntax**

|        |                            |
|:------:|----------------------------|
| Syntax | ObjId.**GetColSortInfo**() |

- **Info**

> **Return**: Object[], 컬럼별 Sort 정보 객체의 배열 집합

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```javascript
// 현재의 Sort 정보를 확인 한다.
var sortInfo = mySheet.GetColSortInfo();
```

- **제공 버전**

| **7.0.13.22** |     |
|---------------|-----|

> **  **