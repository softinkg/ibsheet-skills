# CellAlign Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellAlign Method

---

- **기능**

> 셀에 대한 정렬을 설정하거나 확인한다. 이 속성은 InitColumns 함수에서 설정한 정렬과 달리 화면이 보이는 상태에서 정렬을 단순히 바꾸는 처리를 한다. 설정할 수 있는 값을 아래와 같다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.

|           |             |           |
|:---------:|:-----------:|:---------:|
| 좌측 정렬 | 가운데 정렬 | 우측 정렬 |
|  "Left"   |  "Center"   |  "Right"  |

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Get | ObjId.**GetCellAlign**(Row, Col) |

- **Info**

> **Return**: String, 현재 정렬 값 (Get Method 인 경우)

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |

- **Example**

```javascript
// 해당 셀의 정렬 값을 확인한다.
var align = mySheet.GetCellAlign(1, 1);
alert("셀의 정렬 값은 " + align + "입니다.");
```

- **Syntax**

|        |     |                                         |
|:------:|:---:|-----------------------------------------|
| Syntax | Set | ObjId.**SetCellAlign**(Row, Col, Align) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |
| Align     | String       | 필수   | 정렬 값                           |

- **Example**

```
// 해당 셀을 가운데 정렬로 변경한다.
mySheet.SetCellAlign(1, 1, "Center");
```

- **제공 버전**

> **7.0.0.0**