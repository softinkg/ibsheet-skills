# CellVAlign Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellVAlign Method

---

- **기능**

> 셀 세로 정렬을 설정하거나 확인한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.

- **Syntax**

|        |     |                                   |
|:------:|:---:|-----------------------------------|
| Syntax | Get | ObjId.**GetCellVAlign**(Row, Col) |

- **Info**

> **Return**: String, 세로 정렬 설정값

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |

- **Example**

```
// 특정 셀의 세로 정렬 설정을 확인한다.
Alert(mySheet.GetCellVAlign(1,1));
```

- **Syntax**

|        |     |                                            |
|:------:|:---:|--------------------------------------------|
| Syntax | Set | ObjId.**SetCellVAlign** (Row, Col, valign) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                                 |
| --------- | ------------ | ---- | ----------------------------------- |
| Row       | Long         | 필수   | 해당 셀의 Row Index                     |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName      |
| valign    | String       | 필수   | 셀 세로 정렬 설정값 (top / middle / bottom) |

- **Example**

```
// 특정 셀에 세로 정렬을 top으로 설정한다.
mySheet.SetCellVAlign(1, 1, "top");
// 특정 셀에 세로 정렬을 bottom 으로 설정한다.
mySheet.SetCellVAlign(1, 1, " bottom");
```

- **제공 버전**

7.0.0.0