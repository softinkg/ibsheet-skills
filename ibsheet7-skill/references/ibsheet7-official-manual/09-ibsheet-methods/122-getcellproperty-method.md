# GetCellProperty Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetCellProperty Method

---

- **기능**

> InitColumns 또는 InitCellProperty 에서 설정한 속성의 정보를 확인한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.

- **Syntax**

|        |                                               |
|:------:|-----------------------------------------------|
| Syntax | ObjId.**GetCellProperty**(Row, Col, PropName) |

- **Info**

> **Return**: String/ Boolean/ Integer, 설정한 컬럼의 속성값

| Parameter | Type          | 필수여부 | 설 명                        |
| --------- | ------------- | ---- | -------------------------- |
| Row       | Long          | 필수   | 특정 셀의 Row Index            |
| Col       | Long / String | 필수   | 특정 셀의 컬럼 Index 또는 SaveName |
| PropName  | String        | 필수   | 확인하고자 하는 속성명               |

- **Example**

```javascript
//데이터 타입을 읽어옴
var iType = mySheet.GetCellProperty(1, 1, "Type");
//데이터 SaveName을 읽어옴
var sSaveName = mySheet.GetCellProperty(1, 1, "SaveName");
```

- **제공 버전**

> **7.0.0.0**
>
> **  **