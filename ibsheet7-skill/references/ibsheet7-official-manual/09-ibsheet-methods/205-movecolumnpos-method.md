# MoveColumnPos Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > MoveColumnPos Method

---

- **기능**

> 특정 컬럼을 새로운 컬럼 위치로 이동한다. Event 인자를 1로 설정한 경우 OnBeforeColumnMove Event와 OnAfterColumnMove Event를 발생하므로 OnBeforeColumnMove Event 에서 처리할수 있는 컬럼 이동 취소 기능을 할수 있다. 0으로 설정할 경우 이벤트 없이 컬럼을 이동한다. 다중 컬럼의 경우 \| 문자를 구분자로 이어서 인자를 생성한다.

- **Syntax**

|        |                                                 |
|:------:|-------------------------------------------------|
| Syntax | ObjId.**MoveColumnPos**(Col, NewPos, [Event]) |

- **Info**

> **Return**: Boolean, 이동 성공 여부

| Parameter | Type        | 필수여부 | 설 명                                                                            |
| --------- | ----------- | ---- | ------------------------------------------------------------------------------ |
| Col       | Long/String | 필수   | 이동할 컬럼의 Index 또는 SaveName                                                      |
| NewPos    | Long/String | 필수   | 이동될 위치의 컬럼 Index 또는 SaveName                                                   |
| Event     | Boolean     | 선택   | 이동되면서 발생하는 이벤트인 OnBeforeColumnMove Event와 OnAfterColumn Event를 발생여부, Default=1 |

- **Example**

```
//1컬럼을 9컬럼으로 이동한다.
mySheet.MoveColumnPos(1, 9);
// Index가 1,2인 컬럼들을 Index가 7,8인 컬럼의 위치로 이동한다
mySheet.MoveColumnPos("1|2", "7|8");
//각 컬럼의 SaveName으로 설정한 경우
mySheet.MoveColumnPos("stockNm", "payAmt");
```

- **제공 버전**

|  **7.0.0.0**   |                     |
|:--------------:|---------------------|
| **7.0.13.117** | 다중 컬럼 이동 지원 |

> **  **