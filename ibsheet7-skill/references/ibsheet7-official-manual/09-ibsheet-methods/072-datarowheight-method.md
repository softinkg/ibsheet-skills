# DataRowHeight Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DataRowHeight Method

---

- **기능**

> 모든 데이터 행의 행높이를 설정하거나 확인한다.
>
> 이 속성은 픽셀 단위로 설정하는 값이며, 기본 설정값은 21픽셀이다.

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Get | ObjId.**GetDataRowHeight**() |

- **Info**

> **Return**: Integer, 설정된 높이 값(Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//모든 데이터 행의 높이를 확인한다.
mySheet.GetDataRowHeight();
```

- **Syntax**

|        |     |                                    |
|:------:|:---:|------------------------------------|
| Syntax | Set | ObjId.**SetDataRowHeight**(Height) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명           |
| --------- | ------- | ---- | ------------- |
| Height    | Integer | 필수   | 설정할 데이터행 높이 값 |

- **Example**

```
//모든 데이터 행의 높이를 22 픽셀로 설정한다.
mySheet.SetDataRowHeight(22);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **