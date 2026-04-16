# CheckReverse Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CheckReverse Method

---

- **기능**

> 특정 컬럼에 존재하는 체크박스에 체크된 것은 체크를 풀어주고, 체크되지 않은것은 체크한다.
>
> 단위데이터행 구조인 경우 Col인자에 index를 설정하면 단위데이터 첫번째 행에 대해서 처리하고, SaveName으로 설정할 경우 해당 SaveName인 행에 대해서만 처리 한다.

- **Syntax**

|        |                                                      |
|:------:|------------------------------------------------------|
| Syntax | ObjId.**CheckReverse**(Col, [Editable], [Event]) |

- **Info**

> **Return**: None

| Parameter | Type          | 필수여부 | 설 명                                        |
| --------- | ------------- | ---- | ------------------------------------------ |
| Col       | Long / String | 필수   | 특정 컬럼의 Column Index 또는 SaveName            |
| Editable  | Boolean       | 선택   | 편집가능 불가능을 확인하여 편집가능일때만 변경한다. Default=0     |
| Event     | Boolean       | 선택   | 체크가 바뀔때 OnChange 이벤트를 발생할것인가 여부, Default=0 |

- **Example**

```
// 1컬럼의 체크를 반전한다.
mySheet.CheckReverse(1);
// Edit를 체크하고, Event를 발생시킨다.
mySheet.CheckReverse(1, 1, 1);
```

- **제공 버전**

7.0.0.0