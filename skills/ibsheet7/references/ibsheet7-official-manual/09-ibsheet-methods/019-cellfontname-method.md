# CellFontName Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellFontName Method

---

- **기능**

> 특정 셀에 대해 글자체를 확인하거나 설정한다.
>
> 확인 리턴값 과 설정 인자는 표준 태그의 style 속성에서 사용하는 폰트명을 사용한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.

- **Syntax**

|        |     |                                     |
|:------:|:---:|-------------------------------------|
| Syntax | Get | ObjId.**GetCellFontName**(Row, Col) |

- **Info**

> **Return**: String, 설정 값 (Get Method 인 경우)

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |

- **Example**

```
//글자체를 확인한다
alert(mySheet.GetCellFontName(1, 1));
```

- **Syntax**

|        |     |                                               |
|:------:|:---:|-----------------------------------------------|
| Syntax | Set | ObjId.**SetCellFontName**(Row, Col, FontName) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |
| FontName  | String       | 필수   | 글자체                            |

- **Example**

```
//글자체를 궁서체로 바꾼다.
mySheet.SetCellFontName(1, 1, "Gungsuh")
```

- **제공 버전**

> **7.0.0.0**
>
> **  **