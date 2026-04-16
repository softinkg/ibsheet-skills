# DataRowMerge Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DataRowMerge Method

---

- **기능**

> 모든 데이터 행의 가로 머지 여부를 설정하거나 확인한다.

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Get | ObjId.**GetDataRowMerge**() |

- **Info**

> **Return**: Boolean, 설정된 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//모든 데이터 행의 가로머지를 여부
mySheet.GetDataRowMerge();
```

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Set | ObjId.**SetDataRowMerge**(Merge) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                  |
| --------- | ------- | ---- | -------------------- |
| Merge     | Boolean | 필수   | 머지 허용 여부 Default = 0 |

- **Example**

```
//모든 데이터 행의 가로머지를 허용
mySheet.SetDataRowMerge(1);
```

- **제공 버전**

> **7.0.0.0  **