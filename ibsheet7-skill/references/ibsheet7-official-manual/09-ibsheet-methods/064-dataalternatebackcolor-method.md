# DataAlternateBackColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DataAlternateBackColor Method

---

- **기능**

> 짝수번째 데이터 행의 기본 배경색을 설정하거나 확인한다.
>
> Cfg의 Alternate 속성을 1로 설정시 사용가능하다(Default = 1).
>
> 데이터 행의 짝수번째와 홀수번째를 번갈아 가며 색상을 다르게 표시할 때 사용하는 속성이다. 데이터 행의 배경색은 이 속성과 DataBackColor 함수에 의해 설정된다.
>
> 색상 설정은 WebColor값을 이용하여 설정한다.

- **Syntax**

|        |     |                                       |
|:------:|:---:|---------------------------------------|
| Syntax | Get | ObjId.**GetDataAlternateBackColor**() |

- **Info**

> **Return**: String, 현재 짝수행 색상값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```javascript
// 현재 색상 값을 확인한다.
var color = mySheet.GetDataAlternateBackColor(1,1);
alert("짝수번째행의 색상 값은 " + color + "입니다.");
```

- **Syntax**

|        |     |                                            |
|:------:|:---:|--------------------------------------------|
| Syntax | Set | ObjId.**SetDataAlternateBackColor**(Color) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명      |
| --------- | ------ | ---- | -------- |
| Color     | String | 필수   | 설정할 색상 값 |

- **Example**

```
// 짝수번째행의 배경색을 빨간색으로 변경
mySheet.SetDataAlternateBackColor("#FF0000"); // WebColor
```

- **제공 버전**

> **7.0.0.0**