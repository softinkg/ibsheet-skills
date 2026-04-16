# HeaderBackColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > HeaderBackColor Method

---

- **기능**

> 헤더 행의 바탕색을 설정하거나 확인한다.
>
> 색상 지정은 WebColor값을 사용하여 설정한다.

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Get | ObjId.**GetHeaderBackColor**() |

- **Info**

> **Return**: String, 현재 배경 색상 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//헤더의 배경색 확인한다.
mySheet.GetHeaderBackColor();
```

- **Syntax**

|        |     |                                     |
|:------:|:---:|-------------------------------------|
| Syntax | Set | ObjId.**SetHeaderBackColor**(Color) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명        |
| --------- | ------ | ---- | ---------- |
| Color     | String | 필수   | 헤더행의 배경 색상 |

- **Example**

```
//헤더의 배경색을 빨간색으로 설정한다.
mySheet.SetHeaderBackColor("#FF0000");
```

- **제공 버전**

> **7.0.0.0**
>
> **  **