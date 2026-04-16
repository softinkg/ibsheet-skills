# SelectCell Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SelectCell Method

---

- **기능**

> 특정 셀을 선택한다. 이 함수를 이용할 경우 Edit 가능인 경우 Edit 가능인 경우 Edit 속성를 1로 설정하면 셀이 선택됨과 동시에 편집모드가 된다. Edit 가능은 필요하지 않다면 Edit 속성을 0으로 설정하여 호출한다.
>
> EditText 속성은 Edit 속성이 1일 때 사용되는 값으로 편집 모드시 표시할 문자열을 설정 한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.

- **Syntax**

|        |                                         |
|:------:|-----------------------------------------|
| Syntax | ObjId.**SelectCell**(Row, Col, [Opt]) |

- **Info**

> **Return**: None

| Parameter          | Type            | 필수 여부 | 설 명                                    |
| ------------------ | --------------- | ----- | -------------------------------------- |
| Row                | Number          | 필수    | 선택할 셀의 Row Index                       |
| Col                | Number / String | 필수    | 선택할 셀의 Column Index 또는 SaveName        |
| Opt.Edit           | Boolean         | 선택    | 셀 선택시 편집모드 여부를 설정 Default=0            |
| Opt.EditText       | String          | 선택    | Edit 속성이 1일때 편집상태의 문자열 설정. Defulat= "" |
| Opt.SelectEditText | Boolean         | 선택    | 편집시 기존 값에 대한 select 처리 여부 Default = 1  |
| Opt.Event          | Boolean         | 선택    | OnSelectCell 이벤트 발생 여부 Default = 1     |
| Opt.Focus          | Boolean         | 선택    | 셀 선택후 포커스 처리 여부 Default = 1            |

- **Example**

```
// 2행을 선택하고 그 행 아래에 새로운 행 생성하기
mySheet.SelectCell(2, 0);
mySheet.DataInsert();
```

- **제공 버전**

| **7.0.0.0** |  |
|:--:|----|
| **7.0.4.4** | 편집시 기존 값에 대한 select 처리 여부 설정 기능 추가 (인자 구조 설정방식 변경) |
| **7.0.13.14** | Fous 인자 속성 추가 |