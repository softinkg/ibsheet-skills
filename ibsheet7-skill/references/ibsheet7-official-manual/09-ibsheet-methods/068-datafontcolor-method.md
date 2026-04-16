# DataFontColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DataFontColor Method

---

- **기능**

> 모든 데이터 행의 글자색을 설정하거나 확인한다.
>
> 색상 설정은 WebColor값을 이용하여 설정한다.

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Get | ObjId.**GetDataFontColor**() |

- **Info**

> **Return**: String, 설정된 글자 색상값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//데이터 행의 글자색을 확인한다.
mySheet.GetDataFontColor();
```

- **Syntax**

|        |     |                                   |
|:------:|:---:|-----------------------------------|
| Syntax | Set | ObjId.**SetDataFontColor**(Color) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명      |
| --------- | ------ | ---- | -------- |
| Color     | String | 필수   | 설정할 색상 값 |

- **Example**

```
//데이터 행의 글자색을 빨간색으로 설정한다.
mySheet.SetDataFontColor("#FF0000");
```

- **제공 버전**

> **7.0.0.0**