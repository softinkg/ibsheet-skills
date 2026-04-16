# RowSaveStr Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowSaveStr Method

---

- **기능**

> 행의 데이터를 각 컬럼의 SaveName을 이용하여 저장 시 사용되는 Query String 형태로 조합하여 반환한다.
>
> SaveName1=Value1&SaveName2=Value2&...
>
> 위와 같은 형태로 반환하며, 한글은 UrlEncoding 되어 반환한다.

- **Syntax**

|        |                                    |
|:------:|------------------------------------|
| Syntax | ObjId.**RowSaveStr**(Row, [Opt]) |

- **Info**

> **Return**: String, 행의 데이터

| Parameter          | Type    | 필수여부 | 설 명                         |
| ------------------ | ------- | ---- | --------------------------- |
| Row                | Long    | 필수   | 해당 행의 Row Index             |
| Opt.ValidKeyField  | Boolean | 선택   | KeyField 체크 여부 (Default=1)  |
| Opt.ValidFullInput | Boolean | 선택   | FullInput 체크 여부 (Default=1) |

- **Example**

```javascript
// 1행의 SaveString을 가져온다.
var RowParam = mySheet.RowSaveStr(1);
```

- **제공 버전**

| **7.0.0.0**  |                                              |
|:------------:|----------------------------------------------|
| **7.0.12.4** | ValidKeyField, ValidFullInput 인자 속성 추가 |

> **  **