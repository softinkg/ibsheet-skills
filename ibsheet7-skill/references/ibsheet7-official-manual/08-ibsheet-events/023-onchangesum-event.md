# OnChangeSum Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnChangeSum Event

---

- **기능**

> 합계행에 값이 바뀌었을 때 이벤트가 발생한다.

- **Syntax**

|        |                                                  |
|:------:|--------------------------------------------------|
| Syntax | **function 오브젝트ID_OnChangeSum**(Row,Col) { } |

- **Parameters**

|           |      |                         |
|:---------:|:----:|:-----------------------:|
| Parameter | Type |          설 명          |
|    Row    | Long | 합계행의 상단 Row Index |
|    Col    | Long |   변경 셀의 Col Index   |

- **Example**

```javascript
function mySheet_OnChangeSum(Row, Col) {
//합계 행에 값이 바뀌었을 때, 같은 행의 다른셀에 계산 정보 표시
mySheet.SetSumText(0,2, mySheet.GetSumValue(Col) / 100 + " %");
}
```

- **제공 버전**

7.0.0.0