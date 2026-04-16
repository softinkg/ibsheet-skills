# CellBackColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellBackColor Method

---

- **기능**

> 셀의 배경색을 설정하거나 확인한다.
>
> 그 셀이 데이터 행이든 헤더 행이든 셀의 배경색을 설정하거나 확인할 수 있으며, 셀이 존재하지 않는 경우 에러메시지 없이 배경색 설정은 취소된다. 색상 설정은 WebColor 또는 Basic 16 Color 문자열로 설정한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.

- **Syntax**

|        |     |                                      |
|:------:|:---:|--------------------------------------|
| Syntax | Get | ObjId.**GetCellBackColor**(Row, Col) |

- **Info**

> **Return**: String, 설정된 색상값 (Get Method 인 경우)

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |

- **Example**

```javascript
// 설정된 색상 값을 확인한다.
var color = mySheet.GetCellBackColor(1,1);
alert("셀의 색상 값은 " + color + "입니다.");
```

- **Syntax**

|        |     |                                             |
|:------:|:---:|---------------------------------------------|
| Syntax | Set | ObjId.**SetCellBackColor**(Row, Col, Color) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |
| Color     | String       | 필수   | 색상 값                           |

- **Example**

```
//헤더행의 첫번째 셀의 배경색을 빨간색으로 변경
mySheet.SetCellBackColor(0, 0, "#FF0000"); // WebColor
//데이터행의 셀의 배경색을 헤더행의 첫번째 셀의 배경색과 동일하게 설정
mySheet.SetCellBackColor(1,0, mySheet.GetCellBackColor(0, 0));
//헤더행의 SaveName이 "amt"인 셀의 배경색을 빨간색으로 변경
mySheet.SetCellBackColor(0,"amt", "#FF0000");
```

- **제공 버전**

> **7.0.0.0**
>
> **  **