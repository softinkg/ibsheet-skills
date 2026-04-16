# GetParentRow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetParentRow Method

---

- **기능**

> 트리구조에서 특정 행의 부모 행의 Index를 확인한다.
>
> 부모 행이 없는 경우 -1로 반환한다.

- **Syntax**

|        |                             |
|:------:|-----------------------------|
| Syntax | ObjId.**GetParentRow**(Row) |

- **Info**

> **Return**: Long, 부모 행의 Index

| Parameter | Type | 필수여부 | 설 명         |
| --------- | ---- | ---- | ----------- |
| Row       | Long | 필수   | 대상 행의 Index |

- **Example**

```javascript
// 5번째 행의 부모행을 확인한다.
var parent = mySheet.GetParentRow(5);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **