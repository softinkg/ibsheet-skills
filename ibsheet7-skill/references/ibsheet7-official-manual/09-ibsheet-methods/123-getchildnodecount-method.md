# GetChildNodeCount Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetChildNodeCount Method

---

- **기능**

> 트리구조에서 특정 행의 하위(다음레벨) 노드의 개수를 확인한다.

- **Syntax**

|        |                                  |
|:------:|----------------------------------|
| Syntax | ObjId.**GetChildNodeCount**(Row) |

- **Info**

> **Return**: Integer, 하위 노드의 개수

| Parameter | Type | 필수여부 | 설 명             |
| --------- | ---- | ---- | --------------- |
| Row       | Long | 필수   | 특정 행의 Row Index |

- **Example**

```javascript
//1번째행의 하위노드 개수
var childCount = mySheet.GetChildNodeCount(1);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **