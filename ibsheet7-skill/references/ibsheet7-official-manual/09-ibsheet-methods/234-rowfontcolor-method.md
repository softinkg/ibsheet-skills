# RowFontColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowFontColor Method

---

- **기능**

> 행 전체의 글자색을 설정하거나 확인한다.

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Get | ObjId.**GetRowFontColor**(Row) |

- **Info**

> **Return**: String, 설정 색상 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명       |
| --------- | ---- | ---- | --------- |
| Row       | Long | 필수   | Row Index |

- **Example**

```
//1행의 글자색을 확인한다.
mySheet.GetRowFontColor(1);
```

- **Syntax**

|        |     |                                      |
|:------:|:---:|--------------------------------------|
| Syntax | Set | ObjId.**SetRowFontColor**(Row,Color) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명           |
| --------- | ------ | ---- | ------------- |
| Row       | Long   | 필수   | Row Index     |
| Color     | String | 필수   | WebColor 색상 값 |

- **Example**

```
//1행의 글자색을 회색으로 설정한다.
mySheet.SetRowFontColor(1, "192,192,192");
//2행 글자색을 1행 글자색으로 설정한다.
mySheet.SetRowFontColor(2,mySheet.GetRowFontColor(1));
```

- **제공 버전**

> **7.0.0.0  **