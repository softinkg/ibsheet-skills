# RowExpanded Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowExpanded Method

---

- **기능**

> 트리 형태 일 때 행의 Child Level이 펼쳐져 있는 상태인지 여부를 확인하거나 펼침 여부를 설정한다.
>
> 펼침 여부 설정시(Set Method) Event 인자를 0(false)로 설정하는 경우 관련 이벤트인 OnBeforeExpand, OnAfterExpand 이벤트는 발생하지 않는다.

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Get | ObjId.**GetRowExpanded**(Row) |

- **Info**

> **Return**: Boolean, 행의 자식행들의 펼쳐짐 여부 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명       |
| --------- | ---- | ---- | --------- |
| Row       | Long | 필수   | Row Index |

- **Example**

```
//2행의 펼쳐져 있지 않다면, 2행의 트리를 펼친다.
If(mySheet.GetRowExpanded(2) == 0){
mySheet.SetRowExpanded(2, 1);
}
```

- **Syntax**

|        |     |                                                  |
|:------:|:---:|--------------------------------------------------|
| Syntax | Set | ObjId.**SetRowExpanded**(Row, Expand, [Event]) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                     |
| --------- | ------- | ---- | ----------------------- |
| Row       | Number  | 필수   | 대상 행의 Index             |
| Expand    | Boolean | 필수   | 자식행의 펼쳐짐 여부             |
| Event     | Boolean | 선택   | 관련 이벤트 발생여부 Default = 1 |

- **Example**

```
//2행의 펼쳐져 있지 않다면, 2행의 트리를 펼친다.
If(mySheet.GetRowExpanded(2) == 0){
mySheet.SetRowExpanded(2, 1);
}
```

- **제공 버전**

| **7.0.0.0** |                                        |
|:-----------:|----------------------------------------|
| **7.0.4.2** | Set 메소드의 이벤트 발생여부 인자 추가 |