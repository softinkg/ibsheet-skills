# ReturnCellData Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ReturnCellData Method

---

- **기능**

> 조회된 데이터의 특정 셀의 값을 트랜잭션이 발생하기 이전의 조회된 데이터 되돌린다.
>
> 조회된 데이터로 되돌리지 못하는 경우는 다음과 같다.
>
> 1\. 조회된 데이터가 아닌 경우, 예를 들면 입력 상태의 데이터
>
> 2\. Status 컬럼이 존재하지 않는 경우
>
> 3\. 다음의 데이타 타입인 경우 : Status, Seq
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.

- **Syntax**

|        |                                   |
|:------:|-----------------------------------|
| Syntax | ObjId.**ReturnCellData**(Row,Col) |

- **Info**

> **Return**: None

| Parameter | Type          | 필수여부 | 설 명                             |
| --------- | ------------- | ---- | ------------------------------- |
| Row       | Long          | 필수   | 데이터 셀의 Row Index                |
| Col       | Long / String | 필수   | 데이터 셀의 Column Index 또는 SaveName |

- **Example**

```
//초기 상태로 변경하기
mySheet.ReturnCellData(Row,Col);
```

- **제공 버전**

7.0.0.0