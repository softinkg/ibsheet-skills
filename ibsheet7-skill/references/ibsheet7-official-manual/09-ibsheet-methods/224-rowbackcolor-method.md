# RowBackColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowBackColor Method

---

- **기능**

> 행 전체의 배경색을 설정하거나 확인한다. 데이터 영역의 배경색만 처리한다.행이 존재하지 않는 경우 에러메시지 없이 배경색 설정은 취소되고, 확인 시 0이 반환된다.
>
> 색상 설정은 WebColor 값을 이용하여 설정한다.

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Get | ObjId.**GetRowBackColor**(Row) |

- **Info**

> **Return**: String, 배경 색상 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명       |
| --------- | ---- | ---- | --------- |
| Row       | Long | 필수   | Row Index |

- **Example**

```
//1행의 배경색을 확인한다.
mySheet.GetRowBackColor(1);
```

- **Syntax**

|        |     |                                          |
|:------:|:---:|------------------------------------------|
| Syntax | Set | ObjId.**SetRowBackColor**(Row,BackColor) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명           |
| --------- | ------ | ---- | ------------- |
| Row       | Long   | 필수   | Row Index     |
| BackColor | String | 필수   | WebColor 색상 값 |

- **Example**

```
//1행의 배경색을 회색으로 설정한다.
mySheet.SetRowBackColor(1,"#C0C0C0");
//3행의 배경색을 빨강색으로 설정한다.
mySheet.SetRowBackColor(1,"#FF0000");
//2행 배경색을 1행 배경색으로 설정한다.
mySheet.SetRowBackColor(2, mySheet.GetRowBackColor(1));
```

- **제공 버전**

7.0.0.0