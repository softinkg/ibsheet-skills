# DataBackColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DataBackColor Method

---

- **기능**

> 데이터 행의 기본 배경색을 설정하거나 확인한다.
>
> 데이터 행의 짝수번째와 홀수번째를 번갈아 가며 색상을 다르게 표시할 때 사용하는 속성이다. 데이터 행의 배경색은 이 속성과 DataAlternateBackColor 함수에 의해 설정된다.
>
> 색상 설정은 WebColor값을 이용하여 설정한다.

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Get | ObjId.**GetDataBackColor**() |

- **Info**

> **Return**: String, 현재 배경 색상값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
데이터 행의 배경색을 확인한다.
mySheet.GetDataBackColor();
```

- **Syntax**

|        |     |                                   |
|:------:|:---:|-----------------------------------|
| Syntax | Set | ObjId.**SetDataBackColor**(Color) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명      |
| --------- | ------ | ---- | -------- |
| Color     | String | 필수   | 설정할 색상 값 |

- **Example**

```
데이터 행의 배경색을 흰색으로 설정한다.
mySheet.SetDataBackColor("#FFFFFF");
```

- **제공 버전**

> **7.0.0.0**