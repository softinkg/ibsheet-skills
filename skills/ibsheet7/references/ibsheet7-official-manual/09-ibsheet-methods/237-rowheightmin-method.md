# RowHeightMin Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowHeightMin Method

---

- **기능**

> 모든 행의 최소 높이를 확인하거나 설정한다. 최소 높이는 5픽셀 이하로 할수 없으므로 5픽셀 이상의 값을 설정하도록 한다. 기본값은 21픽셀로 설정되어 있다.

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Get | ObjId.**GetRowHeightMin**() |

- **Info**

> **Return**: Integer, 행의 최소 높이 (Get Method인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//설정한 최소 높이값 확인한다.
mySheet.GetRowHeightMin();
```

- **Syntax**

|        |     |                                      |
|:------:|:---:|--------------------------------------|
| Syntax | Set | ObjId.**SetRowHeightMin**(MinHeight) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명            |
| --------- | ------- | ---- | -------------- |
| MinHeight | Integer | 필수   | 행에 설정 할 최소 높이값 |

- **Example**

```
//최소 높이를 10픽셀로 설정한다.
mySheet.SetRowHeightMin(10);
```

- **제공 버전**

7.0.0.0