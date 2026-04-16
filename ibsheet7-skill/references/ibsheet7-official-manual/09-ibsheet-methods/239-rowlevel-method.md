# RowLevel Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowLevel Method

---

- **기능**

> 행의 트리 레벨을 설정하거나 확인한다.
>
> 트리가 존재하는 경우 행의 트리 레벨을 설정하거나 확인하며 트리 레벨은 0부터 시작한다.

- **Syntax**

|        |     |                            |
|:------:|:---:|----------------------------|
| Syntax | Get | ObjId.**GetRowLevel**(Row) |

- **Info**

> **Return**: Integer, 현재 행의 트리 레벨 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명             |
| --------- | ---- | ---- | --------------- |
| Row       | Long | 필수   | 해당 행의 Row Index |

- **Example**

```
//1행의 트리 레벨을 확인한다.
mySheet.GetRowLevel(1);
```

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Set | ObjId.**SetRowLevel**(Row,Level) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명               |
| --------- | ------- | ---- | ----------------- |
| Row       | Long    | 필수   | 해당 행의 Row Index   |
| Level     | Integer | 필수   | 해당 행의 트리 레벨값(Set) |

- **Example**

```
//트리 레벨을 1 증가 시킨다.
mySheet.SetRowLevel(1,mySheet.GetRowLevel(1) +1);
```

- **제공 버전**

> **7.0.0.0.**