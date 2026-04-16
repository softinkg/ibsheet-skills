# CellValue Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellValue Method

---

- **기능**

> 셀에 값을 설정하거나 확인한다.
>
> 셀의 값을 Format이 적용되지 않은 실제로 저장 시 사용하는 값으로 확인하고, 설정한다. 이 속성을 이용하여 셀에 값을 설정하면 기본적으로 OnChange 이벤트가 발생하며, CellValue 함수의 Flag 인자의 값이 0이면 OnChange이벤트는 발생하지 않고 값이 변경된다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.
>
> Type과 Format 별로 셀의 값은 다음과 같다.

| Type                             | 설명                                    |                                                        |
| -------------------------------- | ------------------------------------- | ------------------------------------------------------ |
| Seq Pass                         | 설정이 불가능한 타입                           |                                                        |
| Status                           | 입력 = "I", 수정 = "U", 삭제 = "D", 조회 = "" |                                                        |
| CheckBox, DummyCheck, RadioCheck | 1 또는 0                                |                                                        |
| Combo ComboEdit                  | 콤보 코드                                 |                                                        |
| Image                            | 해당 이미지의 실제경로                          |                                                        |
| 그외 Type                          | Format                                | 설명                                                     |
| 그외 Type                          | Ymd                                   | 숫자8자리일 때 "yyyy.mm.dd"으로 표현하며 확인 시 숫자 8자리 반환            |
| 그외 Type                          | Ym                                    | 숫자6자리일 때 "yyyy.mm"으로 표현하며 확인 시 숫자 6자리 반환               |
| 그외 Type                          | Md                                    | 숫자4자리일 때 "mm.dd"로 표현하며 확인 시 숫자 4자리 반환                  |
| 그외 Type                          | Hms                                   | 숫자6자리일 때 "hh:mm:ss"로 표현하며 확인 시 숫자 6자리 반환               |
| 그외 Type                          | Hm                                    | 숫자4자리일 때 "hh:mm"로 표현하며 확인 시 숫자 4자리 반환                  |
| 그외 Type                          | YmdHms                                | 숫자14자리일 때 "yyyy.mm.dd hh:mm:ss"으로 표현하며 확인 시 숫자 14자리 반환 |
| 그외 Type                          | YmdHm,                                | 숫자12자리일 때 "yyyy.mm.dd hh:mm"으로 표현하며 확인 시 숫자 12자리 반환    |
| 그외 Type                          | IdNo                                  | 숫자13자리일 때 "######-#######"로 표현하며 확인 시 숫자13자리           |
| 그외 Type                          | SaupNo                                | 숫자10자리일 때 "###-##-#####"로 표현하며 확인 시 숫자10자리             |
| 그외 Type                          | CardNo                                | 숫자14자리일 때 "####-####-####-####"로 표현하며 확인 시 숫자14자리 반환   |
| 그외 Type                          | PostNo                                | 숫자6자리일 때 "###-###"로 표현하며 확인 시 숫자6자리 반환                 |
| 그외 Type                          | Integer                               | "#,##0" 로 표현하며 확인 시 숫자로 반환                             |
| 그외 Type                          | NullInteger                           | "#,###" 로 표현하며 확인 시 숫자로 반환                             |
| 그외 Type                          | Float                                 | "#,##0."+Point개수로 표현하며 확인 시 숫자로 반환                     |
| 그외 Type                          | NullFloat                             | "#,###."+Point개수로 표현하며 확인 시 숫자로 반환                     |

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Get | ObjId.**GetCellValue**(Row, Col) |

- **Info**

> **Return**: String, 셀에 설정된 값 (Get Method 인 경우)

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |

- **Example**

```
//날짜 셀에 값 확인, 결과는 2011/07/15임
alert(mySheet.GetCellValue(1, 4));
```

- **Syntax**

|        |     |                                                  |
|:------:|:---:|--------------------------------------------------|
| Syntax | Set | ObjId.**SetCellValue**(Row, Col, Value, [Opt]) |

- **Info**

> **Return**: None

| Parameter   | Type         | 필수여부 | 설 명                            |
| ----------- | ------------ | ---- | ------------------------------ |
| Row         | Long         | 필수   | 해당 셀의 Row Index                |
| Col         | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |
| Value       | String       | 필수   | 셀에 설정할 값                       |
| Opt.event   | Boolean      | 선택   | OnChange 이벤트 발생 여부 (Default=1) |
| Opt.endEdit | Boolean      | 선택   | 편집 종료 여부 (Default=1)           |
| Opt.nocalc  | Boolean      | 선택   | 소계/누계/합계 재계산 여부 (Default=0)    |

- **Example**

```
//상태 셀을 "삭제" 상태로 설정
mySheet.SetCellValue(1, 0, "D");
//CheckBox에 체크되도록 설정
mySheet.SetCellValue(1, 1, 1);
//숫자 셀에 값 설정, 표시되는 값은 12,345임
mySheet.SetCellValue(1, 2, 12345);
//콤보 셀에 값 설정, 표시되는 값은 콤보 텍스트 임
mySheet.SetCellValue(1, 3, "01");
//날짜 셀에 값 설정, 표시되는 값은 "2011/07/15" 임
mySheet.SetCellValue(1, 4, "2011/07/15");
//소수점 숫자 셀에 값 설정, 소수점 3자리이면 표시되는 값은 123.450 임
// OnChange 이벤트 발생
mySheet.SetCellValue(1,5, 123.450);
// OnChange 이벤트 발생하지 않음
mySheet.SetCellValue(1,5, 123.450, 0);
```

- **제공 버전**

|  **7.0.0.0**   |                                                           |
|:--------------:|-----------------------------------------------------------|
| **7.0.13.102** | Opt 인자 구조 변경. event, endEdit, nocalc 인자 속성 추가 |