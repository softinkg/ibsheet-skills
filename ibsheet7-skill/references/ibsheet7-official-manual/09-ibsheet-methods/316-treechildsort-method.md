# TreeChildSort Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > TreeChildSort Method

---

- **기능**

> 트리 구조의 시트에서 대상 행의 자식 노드에 대한 Sort 처리를 수행 한다.
>
> Sort 처리시 대상 행의 1레벨 하위의 노드에 대해서만 처리한다.

- **Syntax**

|        |                           |
|:------:|---------------------------|
| Syntax | ObjId.**TreeChildSort**() |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                                                |
| --------- | ------ | ---- | -------------------------------------------------- |
| Row       | Number | 필수   | 대상 행의 Index                                        |
| Col       | String | 필수   | Sort 기준 컬럼의 Index 또는 SaveName 을 구분자로 연결한 문자열       |
| SortOrder | String | 선택   | 컬럼에 대한 정렬 방식을 구분자로 연결한 문자열.(ASC, DESC) Default=ASC |

- **Example**

```
// Index가 3인 행의 자식노드를 2번째 컬럼을 기준으로 정렬한다.
mySheet.TreeChildSort(3, 2, "ASC");
```

- **제공 버전**

| **7.0.6.0** |     |
|-------------|-----|

**  **