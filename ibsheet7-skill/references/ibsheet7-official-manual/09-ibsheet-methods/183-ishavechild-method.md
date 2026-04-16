# IsHaveChild Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > IsHaveChild Method

---

- **기능**

> 트리형 데이터에서 특정 행에 Child 레벨의 행이 존재하는지 여부를 확인한다.
>
> Child 레벨이 존재할 때 1를 반환하고, 존재하지 않을 때 0를 반환한다.
>
> IncludeDelRow 인자는 Row 인자에 설정행 행 번호 아래에 존재하는 Child 행 중 "삭제"상태의 행을 포함 할것인가 여부를 의미하며, 1인 경우 "삭제" Child행을 포함하고, 0 인경우 포함하지 않는다. Default=0이다.

- **Syntax**

|        |                                               |
|:------:|-----------------------------------------------|
| Syntax | ObjId.**IsHaveChild**(Row, [IncludeDelRow]) |

- **Info**

> **Return**: Boolean, Child행의 존재 여부.

| Parameter     | Type    | 필수여부 | 설 명                                            |
| ------------- | ------- | ---- | ---------------------------------------------- |
| Row           | Long    | 필수   | 특정 행의 Row Index                                |
| IncludeDelRow | Boolean | 선택   | Child 레벨의 행 중 "삭제" 상태의 행을 포함할것인가 여부, Default=0 |

- **Example**

```javascript
//4행의 Child 존재 여부를 확인한다.
If(mySheet.IsHaveChild(4)) {
alert("4행에 자식 레벨이 존재합니다.");
}else{
alert("4행에 자식 레벨이 존재하지 않습니다.");
}
//4행의 삭제된 Child도 포함하여 확인한다.
var bResult = mySheet.IsHaveChild(4, 1);
```

- **제공 버전**

7.0.0.0