# CellFontColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellFontColor Method

---

- **기능**

> 셀의 글자 색을 확인하거나 설정한다.
>
> 셀이 헤더 영역이든 데이터 영역이든 글자색을 설정할 수 있고, 셀이 존재하지 않는 경우 에러메시지를 표시하지는 않지만 설정은 취소된다.
>
> 색상 설정은 WebColor 또는 Basic 16 Color 문자열로 설정한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.

- **Syntax**

|        |     |                                      |
|:------:|:---:|--------------------------------------|
| Syntax | Get | ObjId.**GetCellFontColor**(Row, Col) |

- **Info**

> **Return**: String, 설정된 색상값 (Get Method 인 경우)

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |

- **Example**

```
//금액이 0보다 작으면 숫자는 붉은색으로 표시한다.
If(mySheet.GetCellValue(1, 2) < 0 ) {
mySheet.SetCellFontColor(1,2,"#FF0000") ;
//금액이 0보다 크면 숫자는 검은색으로 표시한다.
} else {
mySheet.SetCellFontColor(1,2, "#000000");
}
```

- **Syntax**

|        |     |                                             |
|:------:|:---:|---------------------------------------------|
| Syntax | Set | ObjId.**SetCellFontColor**(Row, Col, Color) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |
| Color     | String       | 필수   | 색상 값                           |

- **Example**

```
//금액이 0보다 작으면 숫자는 붉은색으로 표시한다.
If(mySheet.GetCellValue(1, 2) < 0 ) {
mySheet.SetCellFontColor(1,2,"#FF0000") ;
//금액이 0보다 크면 숫자는 검은색으로 표시한다.
} else {
mySheet.SetCellFontColor(1,2, "#000000");
}
```

- **제공 버전**

7.0.0.0