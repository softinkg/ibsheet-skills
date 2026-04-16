# CellSearchValue Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellSearchValue Method

---

- **기능**

> 셀이 조회되었던 당시의 값을 확인한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.
>
> 해당 행이 입력된 행이거나 다음과 같은 Type일때, 값은 공백이다.
>
> Status, DelCheck, Seq, Image

- **Syntax**

|        |                                     |
|:------:|-------------------------------------|
| Syntax | ObjId.**CellSearchValue**(Row, Col) |

- **Info**

> **Return**: String, 조회당시 셀 값

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |

- **Example**

```javascript
// 조회되었던 셀 값을 확인하고, 해당 셀 값을 원래 값으로 되돌린다.
var OrgValue = mySheet.CellSearchValue(Row, Col);
if(OrgValue != mySheet.GetCellValue(Row, Col)) {
mySheet.SetCellValue(Row, Col, OrgValue);
}
```

- **제공 버전**

7.0.0.0