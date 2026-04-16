# CumulateBackColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CumulateBackColor Method

---

- **기능**

> 누계 행의 배경 색상을 확인하거나 설정한다.
>
> 색상 설정은 WebColor 값을 사용하여 설정한다..

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Get | ObjId.**GetCumulateBackColor**() |

- **Info**

> **Return**: String, 현재 누계 색상 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//누계 행 배경색상을 확인
mySheet.GetCumulateBackColor();
```

- **Syntax**

|        |     |                                       |
|:------:|:---:|---------------------------------------|
| Syntax | Set | ObjId.**SetCumulateBackColor**(Color) |

- **Info**

> **Return**: String, 현재 누계 색상 값 (Get Method 인 경우)

| Parameter | Type   | 필수여부 | 설 명        |
| --------- | ------ | ---- | ---------- |
| Color     | String | 필수   | WebColor 값 |

- **Example**

```
//누계 행 배경색상을 녹색으로 설정
mySheet.SetCumulateBackColor("#00FF00");
```

- **제공 버전**

7.0.0.0