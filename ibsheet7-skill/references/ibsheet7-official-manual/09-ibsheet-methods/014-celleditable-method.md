# CellEditable Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellEditable Method

---

- **기능**

> 셀의 Edit 가능 여부를 확인하거나 설정한다.
>
> 해당 셀의 Edit 가능 여부는 Editable 속성에서 설정한 전체 Edit 가능 여부와 InitColumns 함수에서 설정한 Edit설정 및 RowEditable 함수의 설정, 트랜잭션 상태, 자동 계산 여부에 따라 결정된다.
>
> 자동 계산 셀은 CellEditable 설정에 관계 없이 Edit 불가능이다.
>
> 트랜잭션 상태가 "삭제"인경우 컬럼타입이 DelCheck를 제외한 모든 데이터는 Edit 불가능하게 된다. 여타 설정에 관계없이 Edit 불가능한 데이터 타입은 Status, Image, Seq 이다
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.
>
> 위의 경우를 제외한 이속성에 영향을 받는경우 데이터의 Edit 가능여부는 다음과 같다 .

|          |             |             |                  |                         |
|:--------:|:-----------:|:-----------:|:----------------:|:-----------------------:|
| Editable | ColEditable | RowEditable | **CellEditable** | **셀의 Edit 가능 여부** |
|   불가   |    무관     |    무관     |     **무관**     |        **불가**         |
|   가능   |    불가     |    불가     |  **가능/불가**   |      **가능/불가**      |
|   가능   |    가능     |  가능/불가  |  **가능/불가**   |      **가능/불가**      |

- **Syntax**

|        |     |                                     |
|:------:|:---:|-------------------------------------|
| Syntax | Get | ObjId.**GetCellEditable**(Row, Col) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |

- **Example**

```
//1행 2컬럼이 Edit 가능이면 3컬럼도 Edit 가능으로 변경한다.
If(mySheet.GetCellEditable(1, 2) == 1) {
mySheet.SetCellEditable(1, 3, 1);
}
```

- **Syntax**

|        |     |                                           |
|:------:|:---:|-------------------------------------------|
| Syntax | Set | ObjId.**SetCellEditable**(Row, Col, Edit) |

- **Info**

> **Return**: Boolean, 편집 설정 값 (Get Method 인 경우)

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |
| Editable  | Boolean      | 필수   | 편집 가능 여부                       |

- **Example**

```
//1행 2컬럼이 Edit 가능이면 3컬럼도 Edit 가능으로 변경한다.
If(mySheet.GetCellEditable(1, 2) == 1) {
mySheet.SetCellEditable(1, 3, 1);
}
```

- **제공 버전**

> **7.0.0.0**
>
> **  **