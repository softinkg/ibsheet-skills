# SheetHeight Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SheetHeight Method

---

- **기능**

> 전체 높이를 설정하거나 확인한다. 값은 픽셀 단위로 설정한다.

- **Syntax**

|        |     |                            |
|:------:|:---:|----------------------------|
| Syntax | Get | ObjId.**GetSheetHeight**() |

- **Info**

> **Return**: Integer, 설정되어 있는 높이 픽셀값(Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 현재 설정되어있는 전체 높이를 확인한다.
Alert(mySheet.GetSheetHeight());
```

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Set | ObjId.**SetSheetHeight**(Height) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                |
| --------- | ------- | ---- | ------------------ |
| Height    | Integer | 필수   | 설정하고자 하는 시트 높이 픽셀값 |

- **Example**

```
//전체 높이를 800px로 설정한다.
mySheet.SetSheetHeight(800);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **