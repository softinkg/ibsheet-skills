# SumFontColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SumFontColor Method

---

- **기능**

> 합계 행의 글자 색상을 확인하거나 설정한다.
>
> 색상 설정은 WebColor 값을 사용하여 설정한다

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Get | ObjId.**GetSumFontColor**() |

- **Info**

> **Return**: String, 현재 합계행 글자 색상 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//합계행 폰트색상을 확인한다.
mySheet.GetSumFontColor();
```

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Set | ObjId.**SetSumFontColor**(Color) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명        |
| --------- | ------ | ---- | ---------- |
| Color     | String | 필수   | WebColor 값 |

- **Example**

```
//합계 행 폰트색상을 녹색으로 설정
mySheet.SetSumFontColor("#00FF00");
```

- **제공 버전**

7.0.0.0