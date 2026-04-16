# TreeCheckValue Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > TreeCheckValue Method

---

- **기능**

> 트리구조의 시트에서 트리 기준 컬럼에 대한 체크박스 사용 모드인 경우 해당 체크박스의 값을 확인하거나 설정한다.

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Get | ObjId.**GetTreeCheckValue**(Row) |

- **Info**

> **Return**: Number, 해당 체크박스의 값

| Parameter | Type   | 필수여부 | 설 명         |
| --------- | ------ | ---- | ----------- |
| Row       | Number | 필수   | 대상 행의 Index |

- **Example**

```javascript
// Index 가 3인 행에 대한 체크박스 값 확인
var val = mySheet.GetTreeCheckValue(3);
console.log("RowIndex = 3", "Check =", val);
```

- **Syntax**

|        |     |                                                |
|:------:|:---:|------------------------------------------------|
| Syntax | Set | ObjId.**SetTreeCheckValue**(Row, Value, Event) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                                     |
| --------- | ------- | ---- | --------------------------------------- |
| Row       | Number  | 필수   | 대상 행의 Index                             |
| Value     | Boolean | 필수   | 체크박스 설정 값                               |
| Event     | Boolean | 선택   | 설정시 OnTreeCheckChange 이벤트 발생 여부 (기본값:1) |

- **Example**

```
// Index가 3인 행의 트리 컬럼 체크값을 checked 로 설정한다.
mySheet.SetTreeCheckValue(3, 1);
```

- **제공 버전**

| **7.0.9.0** |     |
|-------------|-----|

> **  **