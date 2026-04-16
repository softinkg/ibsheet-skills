# GetDataFirstRow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetDataFirstRow Method

---

- **기능**

> 데이터 행의 시작 인덱스를 확인한다.
>
> 헤더, 필터, 합계행은 인덱스에서 제외되며, 데이터행이 존재하지 않는 경우 -1을 반환한다.

- **Syntax**

|        |                             |
|:------:|-----------------------------|
| Syntax | ObjId.**GetDataFirstRow**() |

- **Info**

> **Return**: Number, 데이터행의 시작 인덱스 (Default=-1)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```javascript
// 데이터행의 시작 인덱스를 확인한다.
var startRow = mySheet.GetDataFirstRow();.
```

- **제공 버전**

| **7.0.13.37** |     |
|---------------|-----|

**  **