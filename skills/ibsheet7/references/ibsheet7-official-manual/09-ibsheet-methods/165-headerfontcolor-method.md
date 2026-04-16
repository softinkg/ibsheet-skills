# HeaderFontColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > HeaderFontColor Method

---

- **기능**

> 헤더 행의 글자색을 설정하거나 확인한다.

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Get | ObjId.**GetHeaderFontColor**() |

- **Info**

> **Return**: String, 현재 설정값(Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//헤더의 글자색을 검은색으로 설정한다.
mySheet.GetHeaderFontColor();
```

- **Syntax**

|        |     |                                     |
|:------:|:---:|-------------------------------------|
| Syntax | Set | ObjId.**SetHeaderFontColor**(Color) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명               |
| --------- | ------ | ---- | ----------------- |
| Color     | String | 필수   | 설정하고자 하는 WebColor |

- **Example**

```
//헤더의 글자색을 검은색으로 설정한다.
mySheet.SetHeaderFontColor("#000000");
```

- **제공 버전**

> **7.0.0.0  **