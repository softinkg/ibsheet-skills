# GetGroupRow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetGroupRow Method

---

- **기능**

> 대상 컬럼을 기준으로 생성된 그룹행을 확인 한다.
>
> 대상 그룹행의 Index를 구분자 "\|"로 연결된 문자열로 반환 한다.

- **Syntax**

|        |                            |
|:------:|----------------------------|
| Syntax | ObjId.**GetGroupRow**(Col) |

- **Info**

> **Return**: String, 현재 설정된 그룹 기준 컬럼 정보

| Parameter | Type           | 필수여부 | 설 명                      |
| --------- | -------------- | ---- | ------------------------ |
| Col       | Number/ String | 필수   | 대상 컬럼의 Index 또는 SaveName |

- **Example**

```
// SaveName이 "sDept"인 컬럼을 기준으로 생성된 그룹행 확인
console.log("GroupRow :", mySheet.GetGroupRow("sDept"));
```

- **제공 버전**

| **7.0.13.22** |     |
|---------------|-----|

> **  **