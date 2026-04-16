# SumFontBold Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SumFontBold Method

---

- **기능**

> 합계 행의 글자를 굵게 할지 여부를 확인하거나 설정한다.
>
> 이 속성을 1로 설정하면 합계 행의 글자를 굵게 표시하고, 0로 설정하면 보통으로 표시한다. 합계행의 글자가 굵으면 해당 컬럼의 다른 데이터와 정렬이 맞지 않는 단점이 있으며, 기본적인 설정값은 0 이다.

- **Syntax**

|        |     |                            |
|:------:|:---:|----------------------------|
| Syntax | Get | ObjId.**GetSumFontBold**() |

- **Info**

> **Return**: Boolean, 현재 폰트 굵기 여부 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//합계행 글자 볼드 설정 확인한다.
mySheet.GetSumFontBold();
```

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Set | ObjId.**SetSumFontBold**(Bold) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명      |
| --------- | ------- | ---- | -------- |
| Bold      | Boolean | 필수   | 폰트 굵기 여부 |

- **Example**

```
//합계 행의 글자 볼드를 설정한다.
mySheet.SetSumFontBold(1);
```

- **제공 버전**

7.0.0.0