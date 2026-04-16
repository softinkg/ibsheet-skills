# SumBackColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SumBackColor Method

---

- **기능**

> 합계 행의 배경 색상을 확인하거나 설정한다.
>
> 색상 설정은 WebColor 값을 사용하여 설정한다.

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Get | ObjId.**GetSumBackColor**() |

- **Info**

> **Return**: String, WebColor 값(Get Method인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//합계행 배경색상 구하기
mySheet.GetSumBackColor();
```

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Set | ObjId.**SetSumBackColor**(Color) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명        |
| --------- | ------ | ---- | ---------- |
| Color     | String | 필수   | WebColor 값 |

- **Example**

```
//합계 행 배경색상을 녹색으로 설정
mySheet.SetSumBackColor("#00FF00");
```

- **제공 버전**

> **7.0.0.0**