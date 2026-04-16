# EditableColorDiff Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > EditableColorDiff Method

---

- **기능**

> 편집이 불가능한 셀을 색상으로 구분하여 표시할지 여부를 확인하거나 설정한다.
>
> 설정 가능한 종류는 다음과 같다.

|      |                                                             |
|:----:|:-----------------------------------------------------------:|
| 종류 |                            설명                             |
|  0   |               편집불가능한 셀을 구분없이 표시               |
|  1   |       편집불가능한 셀을 css에서 설정한 색상으로 표시        |
|  2   | 편집불가능한 셀을 css의 설정값과 기본배경색의 조합으로 표시 |

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Get | ObjId.**GetEditableColorDiff**() |

- **Info**

> **Return**: Integer, 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//편집 불가능한 셀의 표시방법 확인
mySheet.GetEditableColorDiff ();
```

- **Syntax**

|        |     |                                      |
|:------:|:---:|--------------------------------------|
| Syntax | Set | ObjId.**SetEditableColorDiff**(Mode) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명  |
| --------- | ------- | ---- | ---- |
| Mode      | Integer | 필수   | 설정 값 |

- **Example**

```
//편집 불가능한 셀을 구분하지 않음
mySheet.SetEditableColorDiff (0);
```

- **제공 버전**

> **7.0.0.0  **