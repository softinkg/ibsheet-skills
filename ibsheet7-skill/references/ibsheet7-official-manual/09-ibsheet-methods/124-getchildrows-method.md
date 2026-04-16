# GetChildRows Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetChildRows Method

---

- **기능**

> 트리구조에서 특정 행의 자식행들의 Index를 "\|"로 조합하여 반환한다
>
> MaxLevel 인자를 설정하는 경우 해당 레벨까지의 자식 행들까지만 리턴되며 설정하지 않는 경우 모든 자식행들이 리턴된다.

- **Syntax**

|        |                                           |
|:------:|-------------------------------------------|
| Syntax | ObjId.**GetChildRows**(Row, [MaxLevel]) |

- **Info**

> **Return**: String, 대상 자식행들의 문자열 조합

| Parameter | Type    | 필수여부 | 설 명                                        |
| --------- | ------- | ---- | ------------------------------------------ |
| Row       | Long    | 필수   | 대상 행의 Index                                |
| MaxLevel  | Integer | 선택   | 확인할 자식행의 제한 레벨 (-1인 경우 모든 자식행), Default=-1 |

- **Example**

```javascript
// 2번째 행의 모든 자식행 확인
var childRows = mySheet.GetChildRows(2);
// 2번째 행의 자식레벨중 3레벨까지만 확인
var childRows = mySheet.GetChildRows(2, 3);
// 2번째 행의 레벨기준으로 하위 +2레벨까지 확인
var myLevel = mySheet.GetRowLevel(2);
var childRows = mySheet.GetChildRows(2, myLevel+2);
```

- **제공 버전**

> **7.0.0.0  **