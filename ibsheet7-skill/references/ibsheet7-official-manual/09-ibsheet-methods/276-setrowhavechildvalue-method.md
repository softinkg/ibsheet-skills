# SetRowHaveChildValue Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SetRowHaveChildValue Method

---

- **기능**

> 트리구조에서 조회시 HaveChild 속성 설정값을 변경한다.
>
> HaveChild 속성을 설정하는 경우 설정값에 따라서 하위노드 확장 아이콘이 설정이 되는데 이 메소드를 이용하여 설정되어 있는 HaveChild 속성값을 변경 할 수 있다.

- **Syntax**

|        |                                                |
|:------:|------------------------------------------------|
| Syntax | ObjId.**SetRowHaveChildValue**(Row, HaveChild) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명         |     |
| --------- | ------- | ---- | ----------- | --- |
| Row       | Long    | 필수   | 대상 행의 Index |     |
| HaveChild | Boolean | 필수   | 속성 설정값      |     |

- **Example**

```
// 3행의 HaveChild 속성을 0으로 변경한다.
mySheet.SetRowHaveChildValue(3, 0);
```

- **제공 버전**

7.0.0.0