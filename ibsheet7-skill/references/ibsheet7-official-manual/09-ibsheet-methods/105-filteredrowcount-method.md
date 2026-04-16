# FilteredRowCount Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > FilteredRowCount Method

---

- **기능**

> 필터행이 있는 경우 필터가 적용되어 있으면 필터링 된 행의 갯수(출력된 행)를 반환하며 필터가 적용되어 있지 않으면 전체 행 수를 반환한다.
>
> 필터행이 없는 경우 -1을 반환한다.
>
> 행추가 시 추가된 행의 데이터가 필터 조건에 맞지 않을 수 있으나 행 갯수에는 반영된다. 정확한 결과를 얻으려면 행 추가하여 데이터 수정 후 재 필터링을 해야 한다.

- **Syntax**

|        |                              |
|:------:|------------------------------|
| Syntax | ObjId.**FilteredRowCount**() |

- **Info**

> **Return**: Integer. 필터링 된 행 갯수

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```
//필터링 된 행 개수를 가져온다.
Alert(mySheet.FilteredRowCount());
```

- **제공 버전**

> **7.0.0.0**