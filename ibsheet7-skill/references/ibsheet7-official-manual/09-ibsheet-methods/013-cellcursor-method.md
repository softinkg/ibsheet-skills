# CellCursor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellCursor Method

---

- **기능**

> 특정 셀의 마우스 오버시 커서의 모양을 설정한다.
>
> "Default","Pointer" 로 설정이 가능하며 기본적으로 "Default"값이 설정된다.

- **Syntax**

|        |                                   |
|:------:|-----------------------------------|
| Syntax | ObjId.**GetCellCursor**(Row, Col) |

- **Info**

> **Return**: String

| Parameter | Type          | 필수여부 | 설 명                            |
| --------- | ------------- | ---- | ------------------------------ |
| Row       | Long          | 필수   | 특정 셀의 Row Index                |
| Col       | Long / String | 필수   | 특정 셀의 Column Index 또는 SaveName |

- **Example**

```
// (2, 3) 셀의 마우스 커서포인터를 확인한다.
mySheet.GetCellCursor(2, 3);
```

- **Syntax**

|        |                                           |
|:------:|-------------------------------------------|
| Syntax | ObjId.**SetCellCursor**(Row, Col, Cursor) |

- **Info**

> **Return**: None

| Parameter | Type          | 필수여부 | 설 명                            |
| --------- | ------------- | ---- | ------------------------------ |
| Row       | Long          | 필수   | 특정 셀의 Row Index                |
| Col       | Long / String | 필수   | 특정 셀의 Column Index 또는 SaveName |
| Cursor    | String        | 필수   | 마우스 모양 설정                      |

- **Example**

```
// (2, 3) 셀의 마우스 커서포인터를 손가락 모양으로 변경한다.
mySheet.SetCellCursor(2, 3, 'Pointer');
```

- **제공 버전**

> **7.0.13.60**