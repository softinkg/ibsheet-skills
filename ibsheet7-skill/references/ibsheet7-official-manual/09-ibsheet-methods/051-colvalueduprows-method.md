# ColValueDupRows Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ColValueDupRows Method

---

- **기능**

> 중복된 모든 행을 ","로 조합하여 문자열로 반환 한다.
>
> ColValueDup 메소드는 처음으로 중복된 행의 Index만 확인할수 있지만 이 속성은 중복이 시작된행과 모든 중복된 행번호를 확인할 수 있는 기능이다.
>
> 예를 들어 Sheet에 다음과 같이 "기간구분"과 "콘도종류" 2개의 컬럼으로 구성되어 있는 구조라고 할때, ColValueDup=4이다. 1행으로 검사 후 첫 발견된 데이터이므로 결과는 4행이다. 동일한 조건에서 이 속성의 결과는 "3,4,7,8" 이다.
>
> 
>
> **IncludeDelRow** 인자는 트린잭션 상태가 삭제인 행을 중복 검사 대상에 포함할 지 여부를 설정한다. 이 인자값이 true인 경우 삭제인 행을 포함하고, false인 경우 삭제인 행을 포함하지 않는다. 위의 경우 1행이 삭제 상태이고, IncludeDelRow 인자를 false로 설정하면 ColValueDup=3이고, 이 속성의 결과는 "3,7,8"이다.
>
> **IncludeFirstRow** 인자는 중복이 발견된 행의 최초의 기준행을 포함할지 여부를 설정한다. 이 인자 값이 false이면 최초의 기준행을 포함하지 않고, 이 인자 값이 true이면 최초의 기준행들을 ","로 구분하여 문자열로 만들고, 기준행으로 중복된 행들도 ","로 구분하여 문자열로 만든 후 두개 문자열을 "\|"로 조합하여 반환한다.
>
> 위의 경우 최초의 기준행들은 "1,2,5"이고, 중복된 행들은 "3,4,7,8"이다. 따라서 결과는 "1,2,5\|3,4,7,8"이다.
>
> **StartRow** 인자와 **EndRow** 인자는 중복을 검사할 행의 영역을 행Index로 설정하며, 기본적으로 모든 데이터 행을 중복 검사 대상으로 처리한다. 위의 예에서 StartRow=1, EndRow=4로 제한한다면 결과는 "3,4"이다.
>
> 중복된 값이 존재하지 않는 경우 ""을 반환한다.
>
> **IncludeEmpty** 인자가 0인 경우 비교 대상 셀의 모든 값이 빈값인 경우 해당 행은 비교 대상에서 제외 된다.
>
> 2개행 이상의 단위데이터행 구조에서 반환되는 행의 Index는 단위데이터행 구조의 기준이 되는 첫번째 행의 Index를 반환하게 된다. 또한, Col 인자에 Index를 설정할 경우 단위데이터 행의 컬럼 Index 위치의 모든 컬럼에 대해서 처리를 하고 SaveName으로 설정할 경우 해당 SaveName의 컬럼 대해서만 처리를 한다.

- **Syntax**

|        |                                          |
|:------:|:-----------------------------------------|
| Syntax | ObjId.**ColValueDupRows**(Cols, [Opt]) |

- **Info**

> **Return**: String, 중복된 모든 행을 ","로 조합한 문자열

| Parameter           | Type            | 필수여부 | 설 명                                                |
| ------------------- | --------------- | ---- | -------------------------------------------------- |
| Cols                | Number / String | 필수   | 컬럼의 Index 또는 SaveName을 구분자 "\|"로 연결한 문자열           |
| Opt.CaseSensitive   | Boolean         | 선택   | 대/소문자 구분 비교 여부 (Default=1)                         |
| Opt.IncludeDelRow   | Boolean         | 선택   | 트랜잭션 상태가 삭제인 행을 포함 여부. (Default=1)                 |
| Opt.IncludeSumRow   | Boolean         | 선택   | 합계/소계/누계 행 포함 여부. (Default=1)                      |
| Opt.IncludeEmpty    | Boolean         | 선택   | 빈값 포함 여부 (Default=1)                               |
| Opt.IncludeFirstRow | Boolean         | 선택   | 중복된 행의 최초의 행을 포함할지 여부. (Default=0)                 |
| Opt.StartRow        | Number          | 선택   | 중복 검사를 수행 하고자 하는 부분의 첫행의 Index. (Default="첫 행")    |
| Opt.EndRow          | Number          | 선택   | 중복 검사를 수행 하고자 하는 부분의 마지막행 Index. (Default="마지막 행") |

- **Example**

```javascript
//6컬럼,7컬럼의 글자가 중복된 행들(삭제행포함, 최초행미포함, 전체 데이터 영역 검사)
var duprows1 = mySheet.ColValueDupRows("6|7");
//4컬럼,5컬럼에 대해 첫번째 행부터 50번째 행까지의 중복검사(삭제행제외, 최초행포함, 1행~50행)
var duprows2 = mySheet.ColValueDupRows("4|5",{
"IncludeDelRow" : 0,
"IncludeFirstRow" : 1,
"StartRow" : 1,
"EndRow" : 50
});
//가져온 행을 배열로 반든다.
var arrRow = duprows1.split(",");
for (idx=0; idx<arrRow.length-1; idx++){ alert(arrRow[idx] + "행"); }
```

- **제공 버전**

| **7.0.0.0**  |                                                            |
|:------------:|------------------------------------------------------------|
| **7.0.12.3** | 인자 구조 변경, CaseSensitive, IncludeEmpty 인자 속성 추가 |

> **  **