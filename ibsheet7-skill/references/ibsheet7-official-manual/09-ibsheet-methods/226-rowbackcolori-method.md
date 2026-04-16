# RowBackColorI Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowBackColorI Method

---

- **기능**

> 각행의 트랜잭션 상태가 입력인 행의 배경색을 확인하거나 설정한다.
>
> 색상 설정은 WebColor 값을 이용하여 설정한다.

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Get | ObjId.**GetRowBackColorI**() |

- **Info**

> **Return**: String, 설정 색상 (Get Method 인 경우)

| Parameter | Type   | 필수여부 | 설 명           |
| --------- | ------ | ---- | ------------- |
| BackColor | String | 필수   | WebColor 색상 값 |

- **Example**

```
//트렌젝션상태가 입력인 행의 배경색을 확인한다.
mySheet.GetRowBackColorI();
```

- **Syntax**

|        |     |                                       |
|:------:|:---:|---------------------------------------|
| Syntax | Set | ObjId.**SetRowBackColorI**(BackColor) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명           |
| --------- | ------ | ---- | ------------- |
| BackColor | String | 필수   | WebColor 색상 값 |

- **Example**

```
//트렌젝션상태가 입력인 행의 배경색을 회색으로 설정한다.
mySheet.SetRowBackColorI("#C0C0C0");
//트렌젝션상태가 입력인 행을 1행 배경색으로 설정한다.
mySheet.SetRowBackColorI(mySheet.GetRowBackColor(1));
```

- **제공 버전**

7.0.0.0