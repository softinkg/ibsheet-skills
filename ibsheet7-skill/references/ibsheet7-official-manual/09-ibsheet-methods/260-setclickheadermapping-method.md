# SetClickHeaderMapping Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SetClickHeaderMapping Method

---

- **기능**

> 셀 클릭시 셀에 매핑되는 헤더셀의 색상을 변경하도록 설정한다.

- **Syntax**

|        |                                           |
|:------:|-------------------------------------------|
| Syntax | ObjId.**SetClickHeaderMapping**(mapping); |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명      |
| --------- | ------- | ---- | -------- |
| mapping   | Boolean | 필수   | 색상 변경 여부 |

- **Example**

```
// 셀에 매핑되는 헤더셀의 색상을 변경.
mySheet.SetClickHeaderMapping(1);
```

- **제공 버전**

> **7.0.13.99**
>
> **  **