# CellFontSize Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellFontSize Method

---

- **기능**

> 특정 셀에 대해 글자 크기를 확인하거나 설정한다.
>
> 설정 및 확인 값은 픽셀 단위의 값이다..
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.

- **Syntax**

|        |     |                                     |
|:------:|:---:|-------------------------------------|
| Syntax | Get | ObjId.**GetCellFontSize**(Row, Col) |

- **Info**

> **Return**: Integer, 설정 값 (Get Method 인 경우)

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |

- **Example**

```
// 셀의 글자 크기를 확인한다.
Alert(mySheet.GetCellFontSize(1,1));
```

- **Syntax**

|        |     |                                               |
|:------:|:---:|-----------------------------------------------|
| Syntax | Set | ObjId.**SetCellFontSize**(Row, Col, FontSize) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |
| FontSize  | Integer      | 필수   | 설정하고자 하는 글자크기                  |

- **Example**

```
// 글자크기를 20px로 바꾼다.
mySheet.SetCellFontSize(1, 1, 20)
// SaveName이 "sName" 인 셀의 글자크기를 20으로 바꾼다.
mySheet.SetCellFontSize(1,"sName", 20);
```

- **제공 버전**

> **7.0.0.0**

**  **