# DataMove Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DataMove Method

---

- **기능**

> 데이터 행을 원하는 다른 위치로 이동한다. 트리 형태로 설정 될 경우 ChildLevel이 존재하는 경우 선택된 행의 ChildLevel 행도 모두 이동처리한다.
>
> 이 함수는 DataInsert 함수나 DataCopy 함수처럼 신규 행이 생성되는 것이 아니라 기존의 행이 다른 위치로 이동할 뿐이다. 하지만 내부적으로는 복사와 삭제의 작업을 하게된다.
>
> 따라서 ToRow가 FromRow보다 클때는 복사되는 위치에 주의를 기울여야 한다.
>
> 예를 들어 ToRow가 FromRow보다 클때는 다음과 같이 동작하게 된다.
>
> 

- **Syntax**

|        |                                                      |
|:------:|------------------------------------------------------|
| Syntax | ObjId.**DataMove**(ToRow, [FromRow], [RowLevel]) |

- **Info**

> **Return**: Long, 이동된 행의 Top Row Index

| Parameter | Type    | 필수여부 | 설 명                                    |
| --------- | ------- | ---- | -------------------------------------- |
| ToRow     | Long    | 필수   | 이동할 위치의 Row Index                      |
| FromRow   | Long    | 선택   | 선택된 데이터의 Row Index, Default=-1         |
| RowLevel  | Integer | 선택   | 이동 후 선택된 데이터의 트리 레벨 Default="원래 레벨 수준" |

- **Example**

```
//12행을 10행으로 이동한다.
mySheet.DataMove(10, 12);
```

- **제공 버전**

7.0.0.0