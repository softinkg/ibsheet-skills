# ActionMenu Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ActionMenu Method

---

- **기능**

> 컬럼 팝업과 같이 특정 컬럼에 값을 바꾸기 위해 사용하는 메뉴팝업이 아니라 전반적으로 어떤 Action을 처리하기 위해 사용하는 메뉴를 설정하거나 확인한다. 마우스 오른쪽 버튼을 눌렀을 때 팝업 메뉴 형태로 표시되며, 해당하는 위치 컬럼에 이미 컬럼 팝업이 설정되어 있다면 컬럼 팝업이 우선적으로 표시된다. 표시할 메뉴글자를 "\|"로 연결하여 설정하고 메뉴글자가 "\*-"가 설정되면 메뉴가 아닌 중간 구분자로 표시된다.
>
> 표시된 메뉴를 선택하면 OnSelectMenu 이벤트가 발생한다.
>
> 텍스트와 코드를 모두 설정하거나 설정인자를 JSON 객체로 설정하는 경우 GetActionMenu의 리턴값은 JSON객체로 리턴된다.
>
> JSON 객체로 설정하는 경우에 Icon 속성에 이미지 url 을 설정하여 메뉴앞에 아이콘을 출력할 수 있다. 아이콘을 설정하는경우 기본으로 메뉴 앞에 출력되는 Cursor 아이콘의 출력 여부를 두번째 인자에 설정할 수 있으며 이미지 아이콘을 설정하는 경우 기본값은 0으로 커서 아이콘을 출력하지 않는다.
>
> 이미지리스트를 설정해 둔 경우 Icon 속성에 이미지 인덱스를 설정할 수 있다.
>
> 고정코드 사용시 OnSelectMenu에서 별도의 로직 구현 없이 동작할 수 있다.

- **Syntax**

| Syntax | Get | ObjId.**GetActionMenu**()           |
| ------ | --- | ----------------------------------- |
| Syntax | Set | ObjId.**SetActionMenu**(Text, Code) |

- **Info**

> **Return**: String(Object), 설정된 팝업메뉴 (Get Method 인 경우)

| Parameter | Type   | 필수여부 | 설 명                                                                                 |
| --------- | ------ | ---- | ----------------------------------------------------------------------------------- |
| Text      | String | 필수   | 설정할 팝업메뉴 문자열                                                                        |
| Code      | String | 선택   | 설정할 팝업메뉴 코드 문자열 Default="텍스트 문자열" 고정 코드 사용시 OnSelectMenu에서 별도의 로직을 구현 할 필요 없이 사용가능. |
| Icon      | String | 선택   | 메뉴의 커서 아이콘을 원하는 이미지로 설정.                                                            |
| Items     | Array  | 선택   | 메뉴에서 하위 메뉴를 구성.                                                                     |

> \* 고정코드

|                      |                                                |
|:--------------------:|:----------------------------------------------:|
|         Code         |                     설 명                      |
|    _ibColSortAsc    |            대상 컬럼 오름 차순 정렬            |
|   _ibColSortDesc    |            대상 컬럼 내림 차순 정렬            |
|    _ibColHidden     |                대상 컬럼 숨김.                 |
| _ibCancelColHidden  |           헤더메뉴로 숨긴 컬럼 출력            |
| _ibSaveColPosition  | 현재 컬럼정보 저장 (위치, 컬럼 숨김여부, 너비) |
| _ibResetColPosition |              저장된 컬럼정보 삭제              |
|    _ibShowFilter    |                  필터행 출력                   |
|    _ibHideFilter    |                  필터행 숨김                   |

- **Example**

```javascript
// 메뉴만 설정
mySheet.SetActionMenu("입력|행복사|*-|행삭제|Clear|엑셀다운로드");
// 메뉴와 코드 설정
var Text = "입력|행복사|*-|행삭제|Clear|엑셀다운로드";
var Code = "Ins|Copy||Del|Clear|Download";
mySheet.SetActionMenu(Text, Code);
// JSON 객체 설정
var Menu = [
{Text: "입력", Code: "Ins"},
{Text: "행복사", Code: "Copy"},
{Text: "*-"},
{Text: "행삭제", Code: "Delete"},
{Text: "Clear", Code: "Clear"},
{Text: "엑셀다운로드", Code: "Download"}
];
mySheet.SetActionMenu(Menu);
// JSON 객체 계층구조설정
var Menu = [
{Text: "입력", Code: "Ins",
Items : [
{ Text: "첫행입력", Code: "Fins"},
{ Text: "마지막행입력", Code: "Lins"}
]
},
{Text: "행복사", Code: "Copy"},
{Text: "*-"},
{Text: "행삭제", Code: "Delete"},
{Text: "Clear", Code: "Clear"},
{Text: "엑셀다운로드", Code: "Download"}
];
mySheet.SetActionMenu(Menu);
// 이미지 Icon 설정
var Menu = [
{Text: "입력", Code: "Ins", Icon: "../../../image/ess1.gif",
Items : [
{ Text: "첫행입력", Code: "Fins", Icon: "../../../image/ess2.gif"},
{ Text: "마지막행입력", Code: "Lins"}
]
},
{Text: "행복사", Code: "Copy"},
{Text: "*-"},
{Text: "행삭제", Code: "Delete"},
{Text: "Clear", Code: "Clear"},
{Text: "엑셀다운로드", Code: "Download"}
];
mySheet.SetActionMenu(Menu); // 커서 아이콘 출력 안함
mySheet.SetActionMenu(Menu, 1); // 커서 아이콘 출력함
// 설정된 메뉴 확인
var menu = mySheet.GetActionMenu();
//고정코드를 사용하여
//OnSelectMenu 이벤트를 사용하지 않는 방법.
mySheet.SetActionMenu("필터On|*-|필터 Off", "_ibShowFilter||_ibHideFilter");
```

- **제공 버전**

> **7.0.0.0**