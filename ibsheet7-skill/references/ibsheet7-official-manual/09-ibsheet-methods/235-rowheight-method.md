# RowHeight Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowHeight Method

---

- **기능**

> 특정 행의 높이를 설정하거나 확인한다.
>
> 픽셀 단위의 높이를 설정할 수 있고, 행이 존재하지 않는 경우 에러메시지는 표시하지 않지만 처리는 취소된다.

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Get | ObjId.**GetRowHeight**(Row) |

- **Info**

> **Return**: Integer, 현재 행 높이 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명         |
| --------- | ---- | ---- | ----------- |
| Row       | Long | 필수   | 설정할 행 Index |

- **Example**

```
//1행의 높이를 확인한다.
mySheet.GetRowHeight(1);
```

- **Syntax**

|        |     |                                     |
|:------:|:---:|-------------------------------------|
| Syntax | Set | ObjId.**SetRowHeight**(Row, Height) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명         |
| --------- | ------- | ---- | ----------- |
| Row       | Long    | 필수   | 설정할 행 Index |
| Height    | Integer | 필수   | 설정할 행 높이    |

- **Example**

```
//50 픽셀로 높이 수정
mySheet.SetRowHeight(1, 50);
//3행의 높이를 2행의 높이와 동일하게 변경
mySheet.SetRowHeight(3, mySheet.GetRowHeight(2));
```

- **제공 버전**

> **7.0.0.0  **