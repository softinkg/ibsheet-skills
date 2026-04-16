# FindFilterRow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > FindFilterRow Method

---

- **기능**

> 필터행의 인덱스를 반환한다.

- **Syntax**

|        |                           |
|:------:|---------------------------|
| Syntax | ObjId.**FindFilterRow**() |

- **Info**

> **Return**: Long, 필터행의 인덱스 (Default=-1)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```javascript
//필터행의 행 번호를 가져온다.
var filterRow = mySheet.FindFilterRow();
```

- **제공 버전**

| **7.0.13.32** |     |
|---------------|-----|