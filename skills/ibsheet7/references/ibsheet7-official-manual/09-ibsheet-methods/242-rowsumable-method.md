# RowSumable Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowSumable Method

---

- **기능**

> 행의 합계 계산 대상인지 여부를 확인하거나 설정한다.
>
> 해당 속성에 대한 설정은 합계, 소계, 트리소계에 적용 된다.

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Get | ObjId.**GetRowSumable**(Row) |

- **Info**

> **Return**: Boolean, 설정 값

| Parameter | Type   | 필수여부 | 설 명         |
| --------- | ------ | ---- | ----------- |
| Row       | Number | 필수   | 대상 행의 Index |

- **Example**

```javascript
//1행에 대한 합계 계산 대상 여부를 확인 한다..
var sumable = mySheet.GetRowSumable(1);
```

- **Syntax**

|        |     |                                   |
|:------:|:---:|-----------------------------------|
| Syntax | Set | ObjId.**SetRowSumable**(Row, Sum) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명         |
| --------- | ------- | ---- | ----------- |
| Row       | Number  | 필수   | 대상 행의 Index |
| Sum       | Boolean | 필수   | 합계 계산 포함 여부 |

- **Example**

```
//5행을 합계계산에서 제외 한다.
mySheet.SetRowSumable(5, 0);
}
```

- **제공 버전**

> **7.0.0.0**