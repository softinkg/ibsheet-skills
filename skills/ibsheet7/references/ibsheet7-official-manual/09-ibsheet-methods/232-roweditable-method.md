# RowEditable Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowEditable Method

---

- **기능**

> 특정 행의 Edit 가능 여부를 확인하거나 설정한다.
>
> 행의 Edit 가능 여부는 전체 Edit 가능 여부가 가능일 때 변경 가능하다.
>
> 단, ColEditable 설정값이 불가인 경우는 RowEditable 설정이 무시된다
>
> 행의 Edit 가능 여부는 다음과 같이 결정된다.

|          |             |                 |              |                         |
|:--------:|:-----------:|:---------------:|:------------:|:-----------------------:|
| Editable | ColEditable | **RowEditable** | CellEditable | **셀의 Edit 가능 여부** |
|   불가   |    무관     |    **무관**     |     무관     |        **불가**         |
|   가능   |    불가     |    **불가**     |  가능/불가   |      **가능/불가**      |
|   가능   |    가능     |  **가능/불가**  |  가능/불가   |      **가능/불가**      |

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Get | ObjId.**GetRowEditable**(Row) |

- **Info**

> **Return**: Boolean, Edit 가능 여부 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명             |
| --------- | ---- | ---- | --------------- |
| Row       | Long | 필수   | 해당 행의 Row Index |

- **Example**

```
//1행의 Edit 가능 여부를 확인한다.
mySheet.GetRowEditable(1,0);
```

- **Syntax**

|        |     |                                         |
|:------:|:---:|-----------------------------------------|
| Syntax | Set | ObjId.**SetRowEditable**(Row, Editable) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                       |
| --------- | ------- | ---- | ------------------------- |
| Row       | Long    | 필수   | 해당 행의 Row Index           |
| Editable  | Boolean | 필수   | 행의 Edit 가능 여부 (Set일때만 사용) |

- **Example**

```
//1행의 Edit 가능 여부를 0으로 설정한다.
mySheet.SetRowEditable(1,0);
```

- **제공 버전**

> **7.0.0.0  **