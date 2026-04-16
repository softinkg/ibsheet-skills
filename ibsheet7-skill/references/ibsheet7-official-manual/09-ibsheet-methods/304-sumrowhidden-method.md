# SumRowHidden Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SumRowHidden Method

---

- **기능**

> 합계행의 숨기여부를 설정하거나 확인한다.

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Get | ObjId.**GetSumRowHidden**() |

- **Info**

> **Return**: Boolean, 숨김 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//합계행의 숨김 여부를 확인하여 숨겨진 경우 표시되도록 설정한다.
If(mySheet.GetSumRowHidden() == 1) {
mySheet.SetSumRowHidden(0);
}
```

- **Syntax**

|        |     |                                   |
|:------:|:---:|-----------------------------------|
| Syntax | Set | ObjId.**SetSumRowHidden**(Hidden) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명  |
| --------- | ------- | ---- | ---- |
| Hidden    | Boolean | 필수   | 숨김여부 |

- **Example**

```
//합계행의 숨김 여부를 확인하여 숨겨진 경우 표시되도록 설정한다.
If(mySheet.GetSumRowHidden() == 1) {
mySheet.SetSumRowHidden(0);
}
```

- **제공 버전**

> **7.0.0.0**
>
> **  **