# LoadExcelUrl Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > LoadExcelUrl Method

---

- **기능**

> 엑셀 업로드 기능을 처리할 서버 페이지 경로를 확인 및 설정한다.

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Get | ObjId.**GetLoadExcelUrl**() |

- **Info**

> **Return**: String, 설정된 경로값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```javascript
// 엑셀 업로드 설정 경로를 확인한다.
var url = mySheet.GetLoadExcelUrl();
```

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Set | ObjId.**SetLoadExcelUrl**(Url) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명            |
| --------- | ------ | ---- | -------------- |
| Url       | String | 필수   | 설정할 서버 페이지 Url |

- **Example**

```
// 엑셀 업로드 경로를 설정한다.
mySheet.SetLoadExcelUrl("/jsp/LoadExcel.jsp");
```

- **제공 버전**

> **7.0.0.0**
>
> **  **