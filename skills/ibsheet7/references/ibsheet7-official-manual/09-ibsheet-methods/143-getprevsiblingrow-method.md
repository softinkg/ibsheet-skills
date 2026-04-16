# GetPrevSiblingRow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetPrevSiblingRow Method

---

- **기능**

> 트리구조에서 특정 행에 대한 동일 부모, 동일 레벨상의 이전 행의 Index를 확인 한다.
>
> 해당 이전 행이 없는 경우는 -1로 반환 한다..

- **Syntax**

|        |                                  |
|:------:|----------------------------------|
| Syntax | ObjId.**GetPrevSiblingRow**(Row) |

- **Info**

> **Return**: Long, 동일 레벨상 이전 행의 Index

| Parameter | Type | 필수여부 | 설 명         |
| --------- | ---- | ---- | ----------- |
| Row       | Long | 필수   | 대상 행의 Index |

- **Example**

```javascript
// 6번째 행의 동일레벨 상의 이전 행을 확인한다.
var previous = mySheet.GetPrevSiblingRow(6);
```

- **제공 버전**

> **7.0.0.0**