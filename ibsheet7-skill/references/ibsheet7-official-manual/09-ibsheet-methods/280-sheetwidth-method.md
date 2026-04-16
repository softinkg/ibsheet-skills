# SheetWidth Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SheetWidth Method

---

- **기능**

> 전체 너비를 설정하거나 확인한다. 값은 픽셀 단위로 설정한다.

- **Syntax**

|        |     |                           |
|:------:|:---:|---------------------------|
| Syntax | Get | ObjId.**GetSheetWidth**() |

- **Info**

> **Return**: Integer, 설정되어 있는 너비 픽셀값(Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 현재 설정되어있는 전체 너비를 확인한다.
Alert(mySheet.GetSheetWidth());
```

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Set | ObjId.**SetSheetWidth**(Width) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                |
| --------- | ------- | ---- | ------------------ |
| Width     | Integer | 필수   | 설정하고자 하는 시트 너비 픽셀값 |

- **Example**

```
//전체 너비를 800px로 설정한다.
mySheet.SetSheetWidth(800);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **