# ColSaveName Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ColSaveName Method

---

- **기능**

> 특정 컬럼 Index에 해당하는 InitColumns 함수에서 설정한 SaveName을 확인한다.

- **Syntax**

|        |                                     |
|:------:|-------------------------------------|
| Syntax | ObjId.**ColSaveName**(DataRow, Col) |

- **Info**

> **Return**: String, 특정컬럼의 SaveName

| Parameter | Type   | 필수여부 | 설 명            |
| --------- | ------ | ---- | -------------- |
| DataRow   | Number | 필수   | 단위 데이터행의 Index |
| Col       | Number | 필수   | 특정 컬럼의 Index   |

- **Example**

```javascript
//컬럼의 SaveName을 가져온다.
var sSaveName = mySheet.ColSaveName(0, 1);
```

- **제공 버전**

> **7.0.0.0  **