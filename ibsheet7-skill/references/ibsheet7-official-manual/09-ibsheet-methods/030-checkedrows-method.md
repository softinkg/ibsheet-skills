# CheckedRows Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CheckedRows Method

---

- **기능**

> 해당 컬럼에 존재하는 체크박스 중 체크된 행의 개수를 반환한다.
>
> Opt 인자의 RowLevel, ParentRow, Recursive 인자는 트리구조의 시트에서 트리 기준 컬럼에 대한 체크박스 사용 모드에서만 유효한 인자 속성이다.
>
> RowLevel, ParentRow 속성은 동시에 같이 사용할 수 없으며 두 속성 모두 설정이 있는 경우 ParentRow 속성을 우선 처리 한다.
>
> 2개행 이상의 단위데이터행 구조인 경우 Col 인자에 Index를 설정할 경우 모든행에 대해서 처리를 하고 SaveName으로 설정할 경우 해당 SaveName인 행에 대해서만 처리 한다.

- **Syntax**

|        |                                     |
|:------:|-------------------------------------|
| Syntax | ObjId.**CheckedRows**(Col, [Opt]) |

- **Info**

> **Return**: Long, 특정 컬럼에 체크된 행의 개수

| Parameter     | Type          | 필수여부 | 설 명                             |
| ------------- | ------------- | ---- | ------------------------------- |
| Col           | Long / String | 필수   | 특정 컬럼의 Column Index 또는 SaveName |
| Opt.RowLevel  | Number        | 선택   | 처리 대상 트리 레벨 (Default:0)         |
| Opt.ParentRow | Index         | 선택   | 처리 대상 부모 행의 Index               |
| Opt.Recursive | Boolena       | 선택   | 하위 노드에 대한 재귀 처리 여부 (Default:1)  |

- **Example**

```javascript
var cnt1 = mySheet.CheckedRows(1);
console.log("체크된 행의 개수는 ", cnt1, "개 입니다.");
var cnt2 = mySheet.CheckedRows("chkData");
console.log("체크된 행의 개수는 ", cnt2, "개 입니다.");
// 트리기준 컬럼의 체크박스에 대한 사용
// 트리 레벨이 2인 행 가운데 체크된 개수 확인
var res = mySheet.CheckedRows(1, {RowLevel:2, Recursive:0});
// Index가 5인 행의 자식행 가운데 체크된 개수 확인
var arRes = mySheet.CheckedRows (1, {ParentRow:5, Recursive:1});
```

- **제공 버전**

| **7.0.0.0** |                                                      |
| ----------- | ---------------------------------------------------- |
| **7.0.9.0** | 트리 구조의 트리체크에 대한 처리 지원 (RowLevel, ParaenRow 속성 인자 추가) |