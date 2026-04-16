# SaveNameCol Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SaveNameCol Method

---

- **기능**

> InitColumns에서 설정된 SaveName을 이용하여 해당하는 컬럼 번호를 확인한다. SaveName에 해당하는 컬럼이 존재하지 않는 경우 –1을 반환한다.

- **Syntax**

|        |                                 |
|:------:|---------------------------------|
| Syntax | ObjId.**SaveNameCol**(SaveName) |

- **Info**

> **Return**: Long, 컬럼의 Index

| Parameter | Type   | 필수여부 | 설 명    |
| --------- | ------ | ---- | ------ |
| SaveName  | String | 필수   | 저장 변수명 |

- **Example**

```javascript
// 변수명으로 컬럼 번호를 가져온다.
var Col = mySheet.SaveNameCol("stockNm");
```

- **제공 버전**

> **7.0.0.0  **