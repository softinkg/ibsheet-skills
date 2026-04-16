# CellFont Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellFont Method

---

- **기능**

> 특정 셀 또는 영역의 글꼴, 크기, 글자색, 기울임, 볼드, 밑줄 등을 확인하거나 설정한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.
>
> Flag에 사용할수 있는 Font 구분값은 다음과 같다.

|                 |                                |
|:---------------:|:------------------------------:|
|    FLAG 속성    |              설명              |
|   "FontName"    |          글꼴, String          |
|   "FontSize"    |       글자크기, Integer        |
|   "FontColor"   |        글자색상, String        |
|   "FontBold"    |    글자 볼드 여부, Boolean     |
|  "FontItalic"   |   글자 기울임 여부, Boolean    |
| "FontUnderline" |  글자 밑줄 표시 여부, Boolean  |
|  "FontStrike"   | 글자 취소선 표시 여부, Boolean |

- **Syntax**

|        |     |                                                     |
|:------:|:---:|-----------------------------------------------------|
| Syntax | Get | ObjId.**GetCellFont**(Flag, Row1, Col1, Row2, Col2) |

- **Info**

> **Return**: Boolean / String, 설정한 속성 값 (Get Method 인 경우)

| Parameter | Type          | 필수여부 | 설 명                                |
| --------- | ------------- | ---- | ---------------------------------- |
| Flag      | String        | 필수   | 폰트 속성                              |
| Row1      | Long          | 필수   | 영역 시작 셀의 Row Index                 |
| Col1      | Long / String | 필수   | 영역 시작 셀의 Column Index 또는 SaveName  |
| Row2      | Long          | 필수   | 영역 마지막 셀의 Row Index                |
| Col2      | Long / String | 필수   | 영역 마지막 셀의 Column Index 또는 SaveName |

- **Example**

```
//글자크기가 10보다 큰 경우 9사이즈로 변경한다.
If (mySheet.GetCellFont("FontSize", 2,1,2,1) >= 10) {
mySheet.SetCellFont("FontSize", 2,1,2,1,9));
}
```

- **Syntax**

|        |     |                                                            |
|:------:|:---:|------------------------------------------------------------|
| Syntax | Set | ObjId.**SetCellFont**(Flag, Row1, Col1, Row2, Col2, Value) |

- **Info**

> **Return**: None

| Parameter | Type             | 필수여부 | 설 명                                |
| --------- | ---------------- | ---- | ---------------------------------- |
| Flag      | String           | 필수   | 폰트 속성                              |
| Row1      | Long             | 필수   | 영역 시작 셀의 Row Index                 |
| Col1      | Long / String    | 필수   | 영역 시작 셀의 Column Index 또는 SaveName  |
| Row2      | Long             | 필수   | 영역 마지막 셀의 Row Index                |
| Col2      | Long / String    | 필수   | 영역 마지막 셀의 Column Index 또는 SaveName |
| Value     | Boolean / String | 필수   | 폰트속성에 설정할 값                        |

- **Example**

```
//영역에 글자 Bold 설정
mySheet.SetCellFont(« FontBold », 1,1,2,3,1) ;
//영역에 글자 취소선 설정
mySheet.SetCellFont(« FontStrike », 1,1,2,3,1) ;
```

- **제공 버전**

> **7.0.0.0**
>
> **  **