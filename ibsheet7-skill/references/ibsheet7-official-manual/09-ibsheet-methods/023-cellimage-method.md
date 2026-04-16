# CellImage Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellImage Method

---

- **기능**

> Type이 Image이거나 Image 속성을 사용한 경우 해당 셀의 이미지를 확인하거나 설정한다.
>
> 이 속성에 설정되는 값은 이미지파일의 실제 경로를 설정하고,. Type이 맞지 않거나 셀에 이미지가 설정되지 않은 경우 설정이 취소된다.

또한, CellValue 함수로 값을 확인하고 설정할수 있다.

> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Get | ObjId.**GetCellImage**(Row, Col) |

- **Info**

> **Return**: String, 설정된 이미지 경로 (Get Method 인 경우)

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |

- **Example**

```javascript
// 데이터 행을 신규 생성 하고 셀의 이미지와 문자열을 변경한다.
var Row=mySheet.DataInsert();
mySheet.GetCellImage(Row, 1);
```

- **Syntax**

|        |     |                                         |
|:------:|:---:|-----------------------------------------|
| Syntax | Set | ObjId.**SetCellImage**(Row, Col, Image) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |
| Image     | String       | 필수   | 실제 이미지 경로                      |

- **Example**

```javascript
// 데이터 행을 신규 생성 하고 셀의 이미지와 문자열을 변경한다.
var Row=mySheet.DataInsert();
mySheet.SetCellImage(Row, 1, "../image/myImage1.jpg");
// 1컬럼의 SaveName이 "btnAction"인 경우
mySheet.SetCellImage(Row ,"btnAction", "../image/myImage1.jpg");
```

- **제공 버전**

7.0.0.0