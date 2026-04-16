# SelectRow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SelectRow Method

---

- **기능**

> 현재 선택된 셀의 행 Index를 확인하거나 설정한다.
>
> SelectCol 속성과 함께 사용하며, 두 속성을 모두 사용한 SelectCell 함수를 이용할 수 있다.

- **Syntax**

|        |     |                          |
|:------:|:---:|--------------------------|
| Syntax | Get | ObjId.**GetSelectRow**() |

- **Info**

> **Return**: Long, 현재 선택된 행 Index (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//선택된 행을 확인한다.
Alert(mySheet.GetSelectRow());
```

- **Syntax**

|        |     |                                           |
|:------:|:---:|-------------------------------------------|
| Syntax | Set | ObjId.**SetSelectRow**(Row, [UseEvent]) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                                         |
| --------- | ------- | ---- | ------------------------------------------- |
| Row       | Long    | 필수   | 선택할 행 Index                                 |
| UseEvent  | Boolean | 선택   | OnSelectCell 이벤트 발생 여부 Default = 1 (이벤트 발생) |

- **Example**

```
//인덱스가 2인 행을 선택한다.
mySheet.SetSelectRow(2);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **