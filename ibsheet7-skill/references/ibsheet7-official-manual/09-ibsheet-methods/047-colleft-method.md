# ColLeft Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ColLeft Method

---

- **기능**

> 컬럼의 왼쪽 위치를 확인한다.

- **Syntax**

|        |                            |
|:------:|----------------------------|
| Syntax | ObjId.**ColLeft(**Col**)** |

- **Info**

> **Return**: Long, 특정컬럼 왼쪽 위치 값

| Parameter | Type         | 필수여부 | 설 명                             |
| --------- | ------------ | ---- | ------------------------------- |
| Col       | Long /String | 필수   | 특정 컬럼의 Column Index 또는 SaveName |

- **Example**

```javascript
//컬럼의 왼쪽 위치를 파악한다.
var iLeft = mySheet.ColLeft(1);
```

- **제공 버전**

7.0.0.0