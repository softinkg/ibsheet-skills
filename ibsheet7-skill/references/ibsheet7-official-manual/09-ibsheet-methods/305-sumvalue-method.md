# SumValue Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SumValue Method

---

- **기능**

> 합계 셀의 값을 Format이 적용되지 않은 형태로 확인하거나 설정한다.
>
> 자동 계산되는 합계 셀에는 설정이 불가능 하다.

- **Syntax**

|        |     |                                     |
|:------:|:---:|-------------------------------------|
| Syntax | Get | ObjId.**GetSumValue**(DataRow, Col) |

- **Info**

> **Return**: String, 합계 셀의 Value값 (Get Method 인 경우)

| Parameter | Type            | 필수여부 | 설 명                            |
| --------- | --------------- | ---- | ------------------------------ |
| DataRow   | Number          | 필수   | 단위 데이터행의 Index                 |
| Col       | Number / String | 필수   | 합계 셀의 Column Index 또는 SaveName |

- **Example**

```
//첫번째 합계 행의 2컬럼의 값을 읽어온다. 값이 1,234.56 이면
//1234.56이 반환된다..
alert("합계는 " + mySheet.GetSumValue(0, 2) + "입니다.");
```

- **Syntax**

|        |     |                                            |
|:------:|:---:|--------------------------------------------|
| Syntax | Set | ObjId.**SetSumValue**(DataRow, Col, Value) |

- **Info**

> **Return**: None

| Parameter | Type            | 필수여부 | 설 명                            |
| --------- | --------------- | ---- | ------------------------------ |
| DataRow   | Number          | 필수   | 단위 데이터행의 Index                 |
| Col       | Number / String | 필수   | 합계 셀의 Column Index 또는 SaveName |
| Value     | Number / String | 필수   | 포맷 적용 안된 형태의 CellValue 값       |

- **Example**

```
//첫번째 합계 행의 2컬럼의 값을 5432.12 로 바꾼다.
mySheet.SetSumValue(0, 2, 5432.12);
```

- **제공 버전**

7.0.0.0