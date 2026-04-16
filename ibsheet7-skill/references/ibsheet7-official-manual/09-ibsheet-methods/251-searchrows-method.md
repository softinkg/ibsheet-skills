# SearchRows Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SearchRows Method

---

- **기능**

> 조회 XML을 통해서 조회된 전체 행 개수를 확인한다.

- **Syntax**

|        |                        |
|:------:|------------------------|
| Syntax | ObjId.**SearchRows**() |

- **Info**

> **Return**: Long, 조회된 전체 행 개수

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```
//행 개수 확인
alert(mySheet.SearchRows());
```

- **제공 버전**

> **7.0.0.0  **