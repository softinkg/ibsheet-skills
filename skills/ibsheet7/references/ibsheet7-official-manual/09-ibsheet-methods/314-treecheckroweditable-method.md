# TreeCheckRowEditable Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > TreeCheckRowEditable Method

---

- **기능**

> 트리구조의 시트에서 트리 기준 컬럼에 대한 체크박스 사용 모드인 경우 대상 행의 체크박스의 편집가능 여부를 확인하거나 설정한다.

- **Syntax**

|        |     |                                        |
|:------:|:---:|----------------------------------------|
| Syntax | Get | ObjId.**GetTreeCheckRowEditable**(Row) |

- **Info**

> **Return**: Boolean, 컬럼단위 체크박스의 편집 가능 여부

| Parameter | Type   | 필수여부 | 설 명         |
| --------- | ------ | ---- | ----------- |
| Row       | Number | 필수   | 대상 행의 Index |

- **Example**

```javascript
// Index가 3인 행의 체크박스 편집가능여부 확인
var edit = mySheet.GetTreeRowEditable(3);
console.log("RowIndex = 3", "CheckEditable =", edit);
```

- **Syntax**

|        |     |                                              |
|:------:|:---:|----------------------------------------------|
| Syntax | Set | ObjId.**SetTreeCheckRowEditable**(Row, Edit) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명            |
| --------- | ------- | ---- | -------------- |
| Row       | Number  | 필수   | 대상 행의 Index    |
| Edit      | Boolean | 필수   | 체크박스의 편집 가능 여부 |

- **Example**

```
// Index가 3인 행의 트리 컬럼 체크박스의 편집가능여부를 토글한다.
mySheet.SetTreeCheckRowEditable(3, !mySheet.GetTreeCheckRowEditable(3));
```

- **제공 버전**

| **7.0.9.0** |     |
|-------------|-----|

> **  **