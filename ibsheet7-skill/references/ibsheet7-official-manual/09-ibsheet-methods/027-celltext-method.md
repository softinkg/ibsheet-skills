# CellText Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellText Method

---

- **기능**

> 셀의 값을 Format이 적용된 형태로 화면에 보여지는 값 그대로 확인하거나 설정한다.
>
> Type이 Status이고 화면에 보여지는 상태가 "입력"인 경우 이 속성을 호출하면 입력이라는 값 자체를 읽어오고, CellValue 속성을 호출하면 "I"라는 코드값을 반환한다.
>
> Status처럼 모든 Type의 값은 화면에 보여지는 값 그대로 읽어오거나 설정하고, 체크박스가 사용되는 DelCheck, CheckBox와 같은 형태는 체크 여부 이외에 설정된 Text 자체를 확인할 수 있고, 체크여부는 CellValue속성을 이용하여 확인한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.

- **Syntax**

|        |     |                                 |
|:------:|:---:|---------------------------------|
| Syntax | Get | ObjId.**GetCellText**(Row, Col) |

- **Info**

> **Return**: String, 셀에 설정된 값 (Get Method 인 경우)

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |

- **Example**

```
//날짜 셀, 확인 값은 "2011/07/15"
alert(mySheet.GetCellText(1,1));
```

- **Syntax**

|        |     |                                       |
|:------:|:---:|---------------------------------------|
| Syntax | Set | ObjId.**SetCellText**(Row, Col, Text) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |
| Text      | String       | 필수   | 셀에 설정할 값                       |

- **Example**

```
//공백 설정
mySheet.SetCellText(1, 0, "" );
//날짜 셀에 값 설정
mySheet.SetCellText(1, 1, "2011/07/15");
//숫자 셀에 값 설정
mySheet.SetCellText(1, 2, 1,234,567);
//콤보 셀에 콤보코드가 아닌 콤보텍스트 설정
mySheet.SetCellText(1, 3, "원화");
```

- **제공 버전**

7.0.0.0