# MaximumValue Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > MaximumValue Method

---

- **기능**

> Format이 숫자와 관련된 포멧인 Integer, Float, NullInteger, NullFloat일 때, 편집시 입력할 수 있는 최대값을 확인하거나 설정한다.
>
> 최대값이 설정되어있는 셀을 수정시 설정한 값보다 큰값을 입력하면 경고 메세지를 표시한다. (ibmsg 파일의 SYS_MaximumBigValue)
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.
>
> 기본적으로 설정된 최대값과 최소값은 다음과 같다.

| Format              | 최소값                 | **최대값**            |
| ------------------- | ------------------- | ------------------ |
| Integer NullInteger | -999999999999999    | 999999999999999    |
| Float NullFloat     | -999999999999999.00 | 999999999999999.00 |

- **Syntax**

|        |     |                                     |
|:------:|:---:|-------------------------------------|
| Syntax | Get | ObjId.**GetMaximumValue**(Row, Col) |

- **Info**

> **Return**: Long, 설정된 최대값 (Get Method 인 경우)

| Parameter | Type         | 필수여부 | 설 명                        |
| --------- | ------------ | ---- | -------------------------- |
| Row       | Long         | 필수   | 해당 셀의 행 Index              |
| Col       | Long/ String | 필수   | 해당 셀의 컬럼 Index 또는 SaveName |

- **Example**

```
//설정된 숫자포멧의 최대값을 확인한다.
mySheet.GetMaximumValue(1, 12);
```

- **Syntax**

|        |     |                                            |
|:------:|:---:|--------------------------------------------|
| Syntax | Set | ObjId.**SetMaximumValue**(Row, Col, Value) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                        |
| --------- | ------------ | ---- | -------------------------- |
| Row       | Long         | 필수   | 해당 셀의 행 Index              |
| Col       | Long/ String | 필수   | 해당 셀의 컬럼 Index 또는 SaveName |
| Value     | Long         | 필수   | 설정할 최대값                    |

- **Example**

```
//숫자포멧의 최대값을 설정한다.
mySheet.SetMaximumValue(1, 12, 5000);
```

- **제공 버전**

> **7.0.0.0  **