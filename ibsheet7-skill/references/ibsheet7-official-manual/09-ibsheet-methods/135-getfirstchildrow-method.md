# GetFirstChildRow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetFirstChildRow Method

---

- **기능**

> 트리구조에서 특정 행의 첫번째 자식 행의 Index를 확인한다.
>
> 자식행이 없는 경우는 -1를 반환한다.

- **Syntax**

|        |                                 |
|:------:|---------------------------------|
| Syntax | ObjId.**GetFirstChildRow**(Row) |

- **Info**

> **Return**: Long, 첫번째 자식 행의 Index

| Parameter | Type | 필수여부 | 설 명         |
| --------- | ---- | ---- | ----------- |
| Row       | Long | 필수   | 대상 행의 Index |

- **Example**

```javascript
// 2번째 행의 첫번째 자식 행을 확인한다.
var firstChild = mySheet.GetFirstChildRow(2);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **