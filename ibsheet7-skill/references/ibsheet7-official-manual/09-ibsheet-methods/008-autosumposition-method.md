# AutoSumPosition Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > AutoSumPosition Method

---

- **기능**

> 전체 합계/평균의 표시 위치를 설정하거나 확인한다.
>
> 컬럼 타입이 "AutoSum", "AutoAvg"인 경우 전체 합계 또는 전체 평균을 계산하여 표시한다. 표시하는 위치는 다음과 같다

|         |                                             |
|:-------:|:-------------------------------------------:|
| 설정 값 |                    설 명                    |
|    0    |   헤더 바로 아래인 최상단에 고정하여 표시   |
|    1    | 화면에 보이는 영역의 최하단에 고정되어 표시 |

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Get | ObjId.**GetAutoSumPosition**() |

- **Info**

> **Return**: Integer, 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//합계 행을 상단에 표시
mySheet.GetAutoSumPosition();
```

- **Syntax**

|        |     |                                        |
|:------:|:---:|----------------------------------------|
| Syntax | Set | ObjId.**SetAutoSumPosition**(Position) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                 |
| --------- | ------- | ---- | ------------------- |
| Position  | Integer | 필수   | 합계행의 위치 값 Default=1 |

- **Example**

```
//합계 행을 상단에 표시
mySheet.SetAutoSumPosition(0);
```

- **제공 버전**

7.0.0.0