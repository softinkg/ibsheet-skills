# HeaderRowHeight Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > HeaderRowHeight Method

---

- **기능**

> 헤더 행의 행높이를 설정하거나 확인한다. 값은 픽셀 단위로 설정한다

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Get | ObjId.**GetHeaderRowHeight**() |

- **Info**

> **Return**: Integer, 현재 설정값(Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//헤더 행의 높이를 확인
mySheet.GetHeaderRowHeight();
```

- **Syntax**

|        |     |                                      |
|:------:|:---:|--------------------------------------|
| Syntax | Set | ObjId.**SetHeaderRowHeight**(Height) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명          |
| --------- | ------- | ---- | ------------ |
| Height    | Integer | 필수   | 설정하고자 하는 픽셀값 |

- **Example**

```
//헤더 행의 높이를 30 픽셀로 설정.
mySheet.SetHeaderRowHeight(30);
```

- **제공 버전**

7.0.0.0