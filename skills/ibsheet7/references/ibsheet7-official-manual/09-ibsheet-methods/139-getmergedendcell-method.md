# GetMergedEndCell Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetMergedEndCell Method

---

- **기능**

> 전체 머지된 셀중 머지 마지막 셀의 Row와 Col 정보를 Row, Col 형태의 String으로 리턴한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.

- **Syntax**

|        |                                      |
|:------:|--------------------------------------|
| Syntax | ObjId.**GetMergedEndCell**(Row, Col) |

- **Info**

> **Return**: String, Row와 Col 정보를 "Row, Col"형태의 String으로 리턴

| Parameter | Type          | 필수여부 | 설 명                   |
| --------- | ------------- | ---- | --------------------- |
| Row       | Long          | 필수   | 대상 행의 Index           |
| Col       | Long / String | 필수   | 대상이 되는 컬럼 또는 SaveName |

- **Example**

|                                                   |
|---------------------------------------------------|
| var endMergeCell = mySheet.GetMergedEndCell(4,5); |

- **제공 버전**

> **7.0.0.0**