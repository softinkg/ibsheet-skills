# RowHidden Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowHidden Method

---

- **기능**

> 행의 숨기여부를 설정하거나 확인한다.
>
> ‘\|' 구분자로 Row Index를 연결하여 조합하면 다수행의 숨김여부를 설정할 수 있다. (단, 다수행에 대해 Read 기능은 지원되지 않는다. )

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Get | ObjId.**GetRowHidden**(Row) |

- **Info**

> **Return**: Boolean, 설정 값 (Get : 1 이면 숨기 상태, 0이면 보이는 상태)

| Parameter | Type         | 필수여부 | 설 명                                              |
| --------- | ------------ | ---- | ------------------------------------------------ |
| Row       | Long /String | 필수   | 특정 행의 Row Index 혹은 구분자 "\|"로 연결된 문자열 (Set에서만 사용) |

- **Example**

```
//1행이 숨겨진 여부를 확인하여 숨겨진 경우 표시되도록 설정한다.
If(mySheet.GetRowHidden(1)){
mySheet.SetRowHidden(1,0);
}
```

- **Syntax**

|        |     |                                    |
|:------:|:---:|------------------------------------|
| Syntax | Set | ObjId.**SetRowHidden**(Row,Hidden) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                                              |
| --------- | ------------ | ---- | ------------------------------------------------ |
| Row       | Long /String | 필수   | 특정 행의 Row Index 혹은 구분자 "\|"로 연결된 문자열 (Set에서만 사용) |
| Hidden    | Boolean      | 필수   | 숨김여부                                             |

- **Example**

```
//1행이 숨겨진 여부를 확인하여 숨겨진 경우 표시되도록 설정한다.
If(mySheet.GetRowHidden(1)){
mySheet.SetRowHidden(1,0);
}
//다수의 행을 동시에 숨기는 경우
mySheet.SetRowHidden("2|5|7|10", 1);
```

- **제공 버전**

> **7.0.0.0**