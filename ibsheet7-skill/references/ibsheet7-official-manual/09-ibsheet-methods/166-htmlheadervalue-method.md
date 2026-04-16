# HtmlHeaderValue Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > HtmlHeaderValue Method

---

- **기능**

> 헤더의 HTML 타입을 설정하거나 확인한다.
>
> 해당 셋팅값은 GetCellValue 시에 확인할수 없으며, 기존 HeaderText 값이 반환된다. 설정된 태그값을 확인하기 위해서는 GetHtmlHeaderValue 메소드를 통해 확인해야 한다. HTML 태그가 설정된 헤더셀은 헤더 소트가 적용되지 않는다.

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Get | ObjId. **GetHtmlHeaderValue** () |

- **Info**

> **Return**: String, 설정된 태그값을 가져온다. (Get Method 인 경우)

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Row       | Long         | 필수   | 해당 셀의 Row Index                |
| Col       | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName |

- **Example**

```
// (0, 0) Html 타입의 헤더셀의 값을 가져온다.
mySheet.GetHtmlHeaderValue(0, 0);
```

- **Syntax**

|        |     |                                                            |
|:------:|:---:|------------------------------------------------------------|
| Syntax | Set | ObjId. **SetHtmlHeaderValue**(Row, Col, Value, HeaderType) |

- **Info**

> **Return**: None

| Parameter  | Type         | 필수여부 | 설 명                              |
| ---------- | ------------ | ---- | -------------------------------- |
| Row        | Long         | 필수   | 해당 셀의 Row Index                  |
| Col        | Long /String | 필수   | 해당 셀의 Column Index 또는 SaveName   |
| Value      | String       | 필수   | 셀의 값                             |
| HeaderType | boolean      | 선택   | 0:Html 타입, 1:기존 Text (default:0) |

- **Example**

```
// (0, 0) 셀의 타입을 HTML로 바꾸며 값을 checkbox로 변경한다.
mySheet.SetHtmlHeaderValue(0, 0, '< input type=checkbox >');
```

- **제공 버전**

> **7.0.13.68  **