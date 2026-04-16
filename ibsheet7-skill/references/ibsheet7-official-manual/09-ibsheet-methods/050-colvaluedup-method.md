# ColValueDup Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ColValueDup Method

---

- **기능**

> 특정 컬럼 내에 중복된 값이 존재하는지 여부를 확인한다.
>
> 중복된 값이 존재하는 경우 두 번째 중복된 값의 Row Index를 반환한다.
>
> 컬럼을 하나만 사용할 수도 있고, 여러 개를 사용할 경우 "\|" 문자로 조합하여 설정하면, 여러 컬럼의 값이 모두 같은 경우 해당 행의 Index를 반환한다.
>
> **IncludeDelRow** 인자가 1인 경우 트랜잭션 상태가 삭제인 행을 포함하여 중복행을 체크하고, IncludeDelRow인자가 0인 경우 트랜잭션 상태가 삭제인 행을 제외하고 중복행을 체크한다.
>
> **IncludeEmpty** 인자가 0인 경우 비교 대상 셀의 모든 값이 빈값인 경우 해당 행은 비교 대상에서 제외 된다.
>
> 2개행 이상의 단위데이터행 구조에서 반환되는 행의 Index는 단위데이터행 구조의 기준이 되는 첫번째 행의 Index를 반환하게 된다. 또한, Col 인자에 Index를 설정할 경우 단위데이터 행의 컬럼 Index 위치의 모든 컬럼에 대해서 처리를 하고 SaveName으로 설정할 경우 해당 SaveName의 컬럼 대해서만 처리를 한다.
>
> 중복된 값이 존재하지 않는 경우 –1을 반환한다.

- **Syntax**

|        |                                      |
|:------:|--------------------------------------|
| Syntax | ObjId.**ColValueDup**(Cols, [Opt]) |

- **Info**

> **Return**: Number, 중복 행의 Index

| Parameter         | Type            | 필수여부 | 설 명                                      |
| ----------------- | --------------- | ---- | ---------------------------------------- |
| Cols              | Number / String | 필수   | 컬럼의 Index 또는 SaveName을 구분자 "\|"로 연결한 문자열 |
| Opt.CaseSensitive | Boolean         | 선택   | 대/소문자 구분 비교 여부 (Default=1)               |
| Opt.IncludeDelRow | Boolean         | 선택   | 트랜잭션 상태가 삭제인 행을 포함 여부. (Default=1)       |
| Opt.IncludeSumRow | Boolean         | 선택   | 합계/소계/누계 행 포함 여부. (Default=1)            |
| Opt.IncludeEmpty  | Boolean         | 선택   | 빈값 포함 여부 (Default=1)                     |

- **Example**

```javascript
//1컬럼에 중복된 값이 존재하는 행의 Index 확인
var Row = mySheet.ColValueDup("1");
//2,3,7 컬럼에 중복된 값이 존재하는 행의 Index 확인
var Row = mySheet.ColValueDup("2|3|7");
//삭제된 행과 빈값을 제외하고 중복 체크하기
var Row = mySheet.ColValueDup("2|3|7",{
"IncludeDelRow" : 0,
"IncludeEmpty" : 0
});
```

- **제공 버전**

| **7.0.0.0**  |                                             |
|:------------:|---------------------------------------------|
| **7.0.12.3** | 인자 구조 변경, IncludeEmpty 인자 속성 추가 |

> **  **