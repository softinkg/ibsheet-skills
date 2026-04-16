# ShowColumnPopup Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ShowColumnPopup Method

---

- **기능**

> InitColumns 함수를 이용하여 컬럼 팝업 기능이 설정된 컬럼에서 함수를 이용하여 강제로 팝업을 열어주는 기능이다.
>
> 팝업이 열리는 위치는 MousePos를 1로 설정하는 경우 마지막으로 마우스를 클릭한 (X,Y) 좌표에 팝업을 표시하고, MousePos를 0로 설정한 경우는 (Row,Col) 셀의 위치의 아래쪽에 팝업을 표시한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 모든행에 대해서 처리를 하고 SaveName으로 설정할 경우 해당 SaveName이 포함된 행에 대해서만 처리 한다.

- **Syntax**

|        |                                                   |
|:------:|---------------------------------------------------|
| Syntax | ObjId.**ShowColumnPopup**(Row, Col, [MousePos]) |

- **Info**

> **Return**: None

| Parameter | Type            | 필수여부 | 설 명                                    |
| --------- | --------------- | ---- | -------------------------------------- |
| Row       | Number          | 필수   | 선택할 셀의 Row Index                       |
| Col       | Number / String | 필수   | 선택할 셀의 Column Index 또는 SaveName        |
| MousePos  | Boolean         | 선택   | 마지막 마우스 위치 사용 여부, Default=1(마지막 위치 사용) |

- **Example**

```
//현재 셀 위치에 팝업 열기
mySheet.ShowColumnPopup(1, 4, 0)
//마우스를 클릭한 마지막 위치에서 팝업 열기
mySheet.ShowColumnPopup(1, 4,1)
```

- **제공 버전**

7.0.0.0