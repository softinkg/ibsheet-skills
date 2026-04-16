# HeaderFontBold Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > HeaderFontBold Method

---

- **기능**

> 헤더 행의 글자 볼드 여부를 설정하거나 확인한다. 기본적으로 헤더 글자를 볼드하지 않지만 볼드하게 사용할 때 설정한다.

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Get | ObjId.**GetHeaderFontBold**() |

- **Info**

> **Return**: Boolean, 현재 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//헤더의 글자 Bold 설정 확인한다.
mySheet.GetHeaderFontBold();
```

- **Syntax**

|        |     |                                   |
|:------:|:---:|-----------------------------------|
| Syntax | Set | ObjId.**SetHeaderFontBold**(Bold) |

- **Info**

> **Return**: Boolean, 현재 설정 값 (Get Method 인 경우)

| Parameter | Type    | 필수여부 | 설 명                   |
| --------- | ------- | ---- | --------------------- |
| Bold      | Boolean | 필수   | Header행의 Font Bold 여부 |

- **Example**

```
//헤더의 글자를 Bold로 설정한다.
mySheet.SetHeaderFontBold(1);
```

- **제공 버전**

> **7.0.0.0  **