# RowMerge Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowMerge Method

---

- **기능**

> 행의 가로 머지 여부를 확인하거나 설정한다.
>
> 가로 머지가 가능하기 위해서는 전체 머지가 가능하여야 하고, 해당 데이터 행이 존재해야 한다.

- **Syntax**

|        |     |                            |
|:------:|:---:|----------------------------|
| Syntax | Get | ObjId.**GetRowMerge**(Row) |

- **Info**

> **Return**: Boolean, 현재 행의 가로 머지 여부 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명             |
| --------- | ---- | ---- | --------------- |
| Row       | Long | 필수   | 해당 행의 Row Index |

- **Example**

```
// 첫번째 행의 가로 머지를 허용여부를 확인한다.
mySheet.GetRowMerge(1);
```

- **Syntax**

|        |     |                                   |
|:------:|:---:|-----------------------------------|
| Syntax | Set | ObjId.**SetRowMerge**(Row, Merge) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명             |
| --------- | ------- | ---- | --------------- |
| Row       | Long    | 필수   | 해당 행의 Row Index |
| Merge     | Boolean | 필수   | 가로머지 허용 여부      |

- **Example**

```
// 첫번째 행의 가로 머지를 허용하도록 설정한다.
mySheet.SetRowMerge(1, 1);
```

- **제공 버전**

> **7.0.0.0.**