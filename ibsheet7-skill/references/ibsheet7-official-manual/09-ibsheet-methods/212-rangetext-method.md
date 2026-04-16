# RangeText Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RangeText Method

---

- **기능**

> 특정 영역의 셀값을 Format이 적용된 형태로 화면에 보여지는 값 그대로 확인하거나 설정한다.
>
> 그 영역이 데이터 영역이든 헤더 영역이든 셀의 텍스트를 설정하거나 확인할 수 있으며, 영역이 헤더와 데이터 영역을 벗어나는 경우 에러메시지 없이 문자열 설정은 취소되고, 확인 시 0이 반환된다.

- **Syntax**

|  |  |  |
|:--:|:--:|----|
| Syntax | Get | ObjId.**GetRangeText**(Row1,Col1,Row2,Col2,[ColSeparator], [RowSeparator]) |

- **Info**

> **Return**: String, 현재 문자열값(Get Method 인 경우)

| Parameter    | Type   | 필수여부 | 설 명                               |
| ------------ | ------ | ---- | --------------------------------- |
| Row1         | Long   | 필수   | 범위 시작 셀의 Row Index                |
| Col1         | Long   | 필수   | 범위 시작 셀의 Column Index             |
| Row2         | Long   | 필수   | 범위 종료 셀의 Row Index                |
| Col2         | Long   | 필수   | 범위 종료 셀의 Column Index             |
| ColSeparator | String | 선택   | 컬럼과 컬럼 사이를 구분하는 구분자. Default="\|" |
| RowSeparator | String | 선택   | 행과 행 사이를 구분하는 구분자. Default="^"    |

- **Example**

```
//특정 영역의 셀값을 Format이 적용된 형태로 화면에 보여지는 값 그대로 확인한다.
mySheet.GetRangeText(1, 1, 2, 2, "|", "^");
```

- **Syntax**

|  |  |  |
|:--:|:--:|----|
| Syntax | Set | ObjId.**SetRangeText**(sData,Row1,Col1,Row2,Col2, [ColSeparator], [RowSeparator]) |

- **Info**

> **Return**: None

| Parameter    | Type   | 필수여부 | 설 명                               |
| ------------ | ------ | ---- | --------------------------------- |
| sData        | String | 필수   | 문자열                               |
| Row1         | Long   | 필수   | 범위 시작 셀의 Row Index                |
| Col1         | Long   | 필수   | 범위 시작 셀의 Column Index             |
| Row2         | Long   | 필수   | 범위 종료 셀의 Row Index                |
| Col2         | Long   | 필수   | 범위 종료 셀의 Column Index             |
| ColSeparator | String | 선택   | 컬럼과 컬럼 사이를 구분하는 구분자. Default="\|" |
| RowSeparator | String | 선택   | 행과 행 사이를 구분하는 구분자. Default="^"    |

- **Example**

```
//1,1 셀에 A 를 2,2셀에 D를 설정한다.
mySheet.SetRangeText("A|B^C|D", 1, 1, 2, 2, "|", "^");
//1,7 셀부터 5,10 셀까지 ** 로 설정한다.
mySheet.SetRangeText("**", 1, 7, 5, 10);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **