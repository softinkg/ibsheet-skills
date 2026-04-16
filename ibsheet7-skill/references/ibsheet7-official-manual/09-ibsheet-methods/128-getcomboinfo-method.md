# GetComboInfo Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetComboInfo Method

---

- **기능**

> 특정 셀의 콤보 정보를 확인한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.
>
> Flag 인자 값은 다음과 같다.

|                 |                         |
|:---------------:|:-----------------------:|
|     설정값      |          설명           |
|     "Text"      |       콤보텍스트        |
|     "Code"      |        콤보코드         |
|     “Color”     |        콤보컬러         |
|   “Disabled”    |   콤보 선택 불가항목    |
| "SelectedIndex" | 선택된 콤보의Item Index |

- **Syntax**

|        |                                      |
|:------:|--------------------------------------|
| Syntax | ObjId.**GetComboInfo**(Row,Col,Flag) |

- **Info**

> **Return**: String, 콤보 텍스트 또는 코드

| Parameter | Type          | 필수여부 | 설 명                        |
| --------- | ------------- | ---- | -------------------------- |
| Row       | Long          | 필수   | 특정 셀의 Row Index            |
| Col       | Long / String | 필수   | 틀정 셀의 컬럼 Index 또는 SaveName |
| Flag      | String        | 필수   | "Text", "Code" 선택          |

- **Example**

```javascript
//콤보코드와 텍스트를 가져온다.
var sText = mySheet.GetComboInfo(0,2, "Text");
var sCode = mySheet.GetComboInfo(0,2, « Code ») ;
//각각 배열로 구성한다.
var arrText = sText.split("|");
var arrCode = sCode.split("|");
//2행의 2컬럼의 콤보 코드를 이용하여 콤보텍스트를 가져온다.
For(i=0; i<arrCode.length; i++) {
if(mySheet.GetCellValue(2,2) == arrCode[i]) {
alert(arrText[i]);
break;
}
}
```

- **제공 버전**

|  **7.0.0.0**   |                    |
|:--------------:|--------------------|
| **7.0.13.105** | Color 설정 추가    |
| **7.0.13.125** | Disabled 설정 추가 |

> **  **