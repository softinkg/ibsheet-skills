# CellSaveName Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CellSaveName Method

---

- **기능**

> Row, Col 인자의 데이터 셀에 대한 SaveName을 확인 한다.

- **Syntax**

|        |                                   |
|:------:|-----------------------------------|
| Syntax | ObjId.**CellSaveName** (Row, Col) |

- **Info**

> **Return**: String, 해당 셀의 SaveName

| Parameter | Type   | 필수여부 | 설 명                |
| --------- | ------ | ---- | ------------------ |
| Row       | Number | 필수   | 해당 셀의 Row Index    |
| Col       | Number | 필수   | 해당 셀의 Column Index |

- **Example**

```javascript
function mySheet_OnClick(Row, Col, Value, CellX, CellY, CellW, CellH) {
// 클릭한 셀의 SaveName을 확인한다.
var saveName = mySheet.CellSaveName(Row, Col);
}
```

- **제공 버전**

7.0.0.0