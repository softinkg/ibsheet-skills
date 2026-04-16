# CellFontStrike Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellFontStrike Method

---

- **기능**

> 특정 셀 글자에 취소선을 설정한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.
>
> 출력 예) ~~텍스트~~

- **Syntax**

|        |     |                                       |
|:------:|:---:|---------------------------------------|
| Syntax | Get | ObjId.**GetCellFontStrike**(Row, Col) |

- **Info**

> **Return**: Integer, 설정 값 (Get Method 인 경우)

| Parameter | Type           | 필수여부 | 설 명                        |
| --------- | -------------- | ---- | -------------------------- |
| Row       | Number         | 필수   | 대상 셀의 행 Index              |
| Col       | Number /String | 필수   | 대상 셀의 컬럼 Index 또는 SaveName |

- **Example**

```
// 셀의 글자 취소선 설정여부를 확인한다.
Console.log("GetCellFontStrike : ", mySheet.GetCellFontStrike(1,1));
```

- **Syntax**

|        |     |                                                   |
|:------:|:---:|---------------------------------------------------|
| Syntax | Set | ObjId.**SetCellFontStrike**(Row, Col, FontStrike) |

- **Info**

> **Return**: None

| Parameter  | Type           | 필수여부 | 설 명                        |
| ---------- | -------------- | ---- | -------------------------- |
| Row        | Number         | 필수   | 대상 셀의 행 Index              |
| Col        | Number /String | 필수   | 대상 셀의 컬럼 Index 또는 SaveName |
| FontStrike | Boolean        | 필수   | 취소선 설정 여부                  |

- **Example**

```
// 글자 취소선을 설정한다.
mySheet.SetCellFontStrike(1, 1, 1)
// SaveName이 "sName" 인 셀의 글자에 취소선을 설정한다.
mySheet.SetCellFontStrike(1,"sName", 1);
```

- **제공 버전**

> **7.0.0.0**