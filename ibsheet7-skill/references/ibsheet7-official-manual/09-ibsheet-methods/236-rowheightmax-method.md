# RowHeightMax Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowHeightMax Method

---

- **기능**

> 모든 데이터 행의 최대 높이를 확인하거나 설정한다.
>
> 데이터 행의 높이를 자동으로 설정 한 경우에만 적용이 되며 DataRowHeight 보다 작게 설정한 경우 DataRowHeight의 값으로 설정 된다.
>
> 이 기능은 행의 높이를 자동으로 설정 하고 특정 높이 이상 커지지 않게 하고자 하는 경우에 사용한다.

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Get | ObjId.**GetRowHeightMax**() |

- **Info**

> **Return**: Integer, 행의 최대 높이 (Get Method인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//설정한 최소 높이값 확인한다.
mySheet.GetRowHeightMax();
```

- **Syntax**

|        |     |                                      |
|:------:|:---:|--------------------------------------|
| Syntax | Set | ObjId.**SetRowHeightMax**(MaxHeight) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명               |
| --------- | ------- | ---- | ----------------- |
| MaxHeight | Integer | 필수   | 해당 행에 설정 할 최대 높이값 |

- **Example**

```
//최소 높이를 50픽셀로 설정한다.
mySheet.SetRowHeightMax(50);
```

- **제공 버전**

7.0.0.0