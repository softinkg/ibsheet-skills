# CellFontItalic Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellFontItalic Method

---

- **기능**

> 특정 셀의 글자 이탤릭(기울임 글자체) 여부를 확인하거나 설정한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.

- **Syntax**

|        |     |                                       |
|:------:|:---:|---------------------------------------|
| Syntax | Get | ObjId.**GetCellFontItalic**(Row, Col) |

- **Info**

> **Return**: Boolean, 설정 값 (Get Method 인 경우)

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |

- **Example**

```
//특정 셀의 이탤릭체 여부를 확인한다.
Alert(mySheet.GetCellFontItalic(1, 1));
```

- **Syntax**

|        |     |                                               |
|:------:|:---:|-----------------------------------------------|
| Syntax | Set | ObjId.**SetCellFontItalic**(Row, Col, Italic) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |
| Italic    | Boolean      | 필수   | 이탤릭 여부                         |

- **Example**

```
//특정 셀에 글자를 이탤릭체로 설정한다.
mySheet.SetCellFontItalic(1, 1,1)
```

- **제공 버전**

> **7.0.0.0**