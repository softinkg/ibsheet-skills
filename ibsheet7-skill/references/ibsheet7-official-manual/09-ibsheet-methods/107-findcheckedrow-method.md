# FindCheckedRow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > FindCheckedRow Method

---

- **기능**

> 대상 컬럼의 체크된 행의 Index를 구분자 "\|"로 연결한 문자열 또는 배열집합을 반환한다.
>
> Opt 인자의 RowLevel, ParentRow, Recursive 인자는 트리구조의 시트에서 트리 기준 컬럼에 대한 체크박스 사용 모드에서만 유효한 인자 속성이다.
>
> RowLevel, ParentRow 속성은 동시에 같이 사용할 수 없으며 두 속성 모두 설정이 있는 경우 ParentRow 속성을 우선 처리 한다.
>
> 2개행 이상의 단위데이터행 구조인 경우 Col 인자에 Index를 설정할 경우 모든행에 대해서 처리를 하고 SaveName으로 설정할 경우 해당 SaveName인 행에 대해서만 처리 한다.

- **Syntax**

|        |                                        |
|:------:|----------------------------------------|
| Syntax | ObjId.**FindCheckedRow**(Col, [Opt]) |

- **Info**

> **Return**: String|Array, 체크된 행번호를 "|" 연결한 문자열 또는 배열

| Parameter       | Type            | 필수여부 | 설 명                            |
| --------------- | --------------- | ---- | ------------------------------ |
| Col             | Number / String | 필수   | 특정 컬럼의 Index 또는 SaveName       |
| Opt.RowLevel    | Number          | 선택   | 처리 대상 트리 레벨 (Default:0)        |
| Opt.ParentRow   | Index           | 선택   | 처리 대상 부모 행의 Index              |
| Opt.Recursive   | Boolena         | 선택   | 하위 노드에 대한 재귀 처리 여부 (Default:1) |
| Opt.ReturnArray | Boolean         | 선택   | 배열집합 반환 여부 (Default:0)         |

- **Example**

```javascript
//체크된 행번호를 가져온다.
//인자->1, 결과->1|3|4|5|6
var sRow = mySheet.FindCheckedRow(1);
var sRow = mySheet.FindCheckedRow("pass_yn");
// 트리기준 컬럼의 체크박스에 대한 사용
// 트리 레벨이 2인 행 가운데 체크된 목록 산출
var res = mySheet.FindCheckedRow(1, {RowLevel:2, Recursive:0});
// Index가 5인 행의 자식행 가운데 체크된 목록을 배열집합으로 산출
var arRes = mySheet.FindCheckedRow(1, {
ParentRow:5,
Recursive:1,
ReturnArray:1
});
```

- **제공 버전**

| **7.0.0.0** |                                                                                    |
| ----------- | ---------------------------------------------------------------------------------- |
| **7.0.9.0** | 트리 구조의 트리체크에 대한 처리 지원 (RowLevel, ParaenRow 속성 인자 추가) 반환값 형태 설정 기능 추가 (ReturnArray) |

> **  **