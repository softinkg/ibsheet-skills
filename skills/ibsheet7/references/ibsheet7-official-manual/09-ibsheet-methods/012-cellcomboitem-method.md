# CellComboItem Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellComboItem Method

---

- **기능**

> 특정 셀의 Combo 항목만 다른 경우 Combo항목을 개별 설정한다.
>
> 기본적은 컬럼 전체의 콤보 항목은 InitColumns함수를 이용하여 설정하고, 특정 셀만 항목이 다른 경우 이 함수를 이용한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.

- **Syntax**

|        |                                        |
|:------:|----------------------------------------|
| Syntax | ObjId.**CellComboItem**(Row, Col,info) |

- **Info**

> **Return**: None

| Parameter | Type          | 필수여부 | 설 명                                                                   |
| --------- | ------------- | ---- | --------------------------------------------------------------------- |
| Row       | Long          | 필수   | 특정 셀의 Row Index                                                       |
| Col       | Long / String | 필수   | 특정 셀의 Column Index 또는 SaveName                                        |
| info      | Object        | 필수   | 변경할 Combo item 내용을 구분자 "\|"로 연결된 문자열을 만들어 ComboCode와 ComboText로 값을 설정 |

- **Example**

```javascript
//특정 셀의 콤보 항목 바꾸기
var info = {"ComboCode":"사장|과장|대리","ComboText":"A|B|C"};
mySheet.CellComboItem(1,2,info);
//초기 설정값으로 되돌린다.(InitColumns 설정값)
var info = {"ComboCode":"","ComboText":""};
mySheet.CellComboItem(1,2,info);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **