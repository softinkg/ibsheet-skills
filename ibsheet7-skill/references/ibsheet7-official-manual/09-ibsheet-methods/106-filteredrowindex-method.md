# FilteredRowIndex Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > FilteredRowIndex Method

---

- **기능**

> 필터행이 있는 경우 필터가 적용되어 있으면 필터링 된 행의 인덱스를, 필터가 적용되어 있지 않으면 전체 행의 인덱스를 배열로 반환한다.

- **Syntax**

|        |                               |
|:------:|-------------------------------|
| Syntax | ObjId.**FilteredRowIndex** () |

- **Info**

> **Return**: Array. 필터링 된 행의 인덱스 배열

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```
//필터링 된 행 인덱스 배열을 가져온다.
Alert(mySheet.FilteredRowIndex ());
```

- **제공 버전**

| **7.0.13.113** |     |
|----------------|-----|