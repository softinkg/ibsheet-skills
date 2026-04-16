# InitCellProperty Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > InitCellProperty Method

---

- **기능**

> 조회 또는 행 추가 후 특정 셀의 속성 정의를 기본 컬럼 속성 정의와 다르게 하고자 하는 경우에 이 함수를 사용한다.
>
> (단, 날짜포맷 설정은 Ymd, Ym, Md, YmdHms, YmdHm 포맷에 대하여 설정이 가능하다.)
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.
>
> InitColumns Method에서 정의한 컬럼의 타입이 Seq, Status, DelCheck, AutoSum, AutoAvg 인 경우는 해당 함수를 사용 할 수 없으며 설정이 가능한 Type은 다음과 같다.

| Type       | 설명                                       |
|:-----------|--------------------------------------------|
| Button     | 버튼 형태를 표현하는 데이터 타입           |
| CheckBox   | CheckBox 형태 데이터                       |
| Combo      | Edit 불가능 Combo 데이터                   |
| ComboEdit  | 자동완성형태의 Combo 데이터                |
| Date       | 날짜형 타입                                |
| DummyCheck | 이벤트를 발생하지 않는 체크박스 데이터타입 |
| Float      | 실수형 타입                                |
| Html       | Html 태그형태를 표현하는 데이터            |
| Image      | Edit 불가능한 단순 이미지 표현 형태 데이터 |
| Int        | 정수형 타입                                |
| Popup      | 팝업을 사용한 데이터                       |
| Text       | 기본 문자열 데이터                         |

> 이 함수에서 설정이 가능한 속성은 다음과 같다.

| 속성                 | 타입      | 설명                                                                                                                                                                                                                                                                                                     |
| ------------------ | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Type               | String  | 컬럼의 데이터 타입(필수)                                                                                                                                                                                                                                                                                         |
| AcceptKeys         | String  | 입력허용키 설정 "N" : 숫자만 허용 "E" : 영문만 허용 “K” : 한글만 허용 "N\|E" : 숫자, 영문만 허용 "N\|E\|[사용자정의문자]" : 숫자, 영문과 사용자정의문자로 설정한 문자 허용 예) "N\|[abc!]" 설정 시 숫자와 a, b, c, ! 문자만 입력 가능 사용자 정의 문자열은 꼭 대괄호로 묶어서 설정해야 하며 사용자정의문자와 숫자,영문 설정문자의 합집합으로 처리된다. AcceptKeys 와 ExceptKeys를 둘다 설정하고 설정키 내에 동일 문자가 있는 경우 해당 문자는 입력불가 처리된다. |
| Align              | String  | 데이터의 정렬                                                                                                                                                                                                                                                                                                |
| ApproximateType    | Number  | 근사값처리방식 (1:반올림, 2:내림, 3:올림)                                                                                                                                                                                                                                                                            |
| ComboCode          | String  | 콤보 리스트의 코드 집합                                                                                                                                                                                                                                                                                          |
| ComboDisabled      | String  | 콤보의 선택 불가능 항목                                                                                                                                                                                                                                                                                          |
| ComboText          | String  | 콤보 리스트의 문자열 집합                                                                                                                                                                                                                                                                                         |
| Cursor             | String  | 마우스 모양 설정                                                                                                                                                                                                                                                                                              |
| CustomDate         | Number  | 사용자 정의 날짜 사용여부                                                                                                                                                                                                                                                                                         |
| Edit               | Boolean | 편집가능 여부                                                                                                                                                                                                                                                                                                |
| EditLen            | Number  | 데이터의 입력가능한 글자수                                                                                                                                                                                                                                                                                         |
| EmptyToReplaceChar | String  | 빈값인 경우 대체하여 보여줄 문자 설정                                                                                                                                                                                                                                                                                  |
| ExceptKeys         | String  | 입력제외키 설정 "N" : 숫자 입력 불가 "E" : 영문 입력 불가 "N\|E" : 숫자, 영문 입력 불가 "N\|E\|[사용자정의문자]" : 숫자, 영문과 사용자정의문자로 설정한 문자 입력 불가 예) "N\|[abc!]" 설정 시 숫자와 a, b, c, ! 문자만 입력 불가 사용자 정의 문자열은 꼭 대괄호로 묶어서 설정해야 하며 사용자정의문자와 숫자,영문 설정문자의 합집합으로 처리된다. AcceptKeys 와 ExceptKeys를 둘다 설정하고 설정키 내에 동일 문자가 있는 경우 해당 문자는 입력불가 처리된다.     |
| Format             | String  | 데이터의 Mask 적용 형태                                                                                                                                                                                                                                                                                        |
| FormatFix          | Boolean | GetCellValue 시 GetCellText 값을 반환 할지 여부 (Default=0) 특히 True 로 설정시 저장할 때 Format 이 설정된 상태로 저장한다.                                                                                                                                                                                                          |
| HoverUnderline     | Boolean | 마우스오버시 언더라인 여부                                                                                                                                                                                                                                                                                         |
| Image              | String  | 이미지의 경로                                                                                                                                                                                                                                                                                                |
| ImgAlign           | String  | 이미지 표시 위치                                                                                                                                                                                                                                                                                              |
| ImgHeight          | Number  | 이미지 높이                                                                                                                                                                                                                                                                                                 |
| ImgWidth           | Number  | 이미지 너비                                                                                                                                                                                                                                                                                                 |
| InputCaseSensitive | Number  | 입력시 영문에 대한 대소구문 자동 치환 처리에 대한 설정 0 : 별도 처리 하지 않음 (기본값) 1 : 대문자로 치환 2 : 소문자로 치환                                                                                                                                                                                                                          |
| ItemCode           | String  | 멀티체크 아이템의 코드를 구분자 "\|"로 연결한 문자열                                                                                                                                                                                                                                                                        |
| ItemText           | String  | 멀티체크 아이템의 텍스트를 구분자 "\|"로 연결한 문자열                                                                                                                                                                                                                                                                       |
| MaxCheck           | Number  | 멀티체크의 최대 선택 개수 설정                                                                                                                                                                                                                                                                                      |
| MaximumValue       | Number  | 숫자포맷일 때 편집시 입력할 수 있는 최대값                                                                                                                                                                                                                                                                               |
| MinimumValue       | Number  | 숫자포맷일 때 편집시 입력할 수 있는 최소값                                                                                                                                                                                                                                                                               |
| MultiLineText      | Boolean | 다중라인 입력여부                                                                                                                                                                                                                                                                                              |
| PointCount         | Number  | 컬럼타입이 Float 인 경우 소수점 이하의 자리수                                                                                                                                                                                                                                                                           |
| PopupButton        | Boolean | 팝업버튼 표시 여부                                                                                                                                                                                                                                                                                             |
| PopupCode          | String  | 팝업메뉴의 코드 집합                                                                                                                                                                                                                                                                                            |
| PopupText          | String  | 팝업메뉴의 문자열 집합                                                                                                                                                                                                                                                                                           |
| RadioIcon          | Number  | 데이터 셀내의 체크박스 계열의 이미지 모양 설정                                                                                                                                                                                                                                                                             |
| ZeroToReplaceChar  | String  | 값이 0인 경우 대체하여 보여줄 문자 설정                                                                                                                                                                                                                                                                                |

> 각 속성의 상세 설명은 InitColumns Method 설명을 참조 한다.
>
> 이 함수를 사용하기 위해서는 Type을 필수로 설정 해야 한다.

- **Syntax**

|        |                                             |
|:------:|---------------------------------------------|
| Syntax | ObjId.**InitCellProperty**(Row, Col, info); |

- **Info**

> **Return**: None

| Parameter | Type          | 필수여부 | 설 명                         |
| --------- | ------------- | ---- | --------------------------- |
| Row       | Long          | 필수   | 대상 행의 Index                 |
| Col       | Long / String | 필수   | 대상이 되는 컬럼 Index 또는 SaveName |
| info      | Object        | 필수   | 셀의 속성 정의 객체                 |

- **Example**

```javascript
// Text 컬럼 타입으로 변경
var info = {Type: "Text", Align: "Center", Edit: 0};
mySheet.InitCellProperty(2, "sCombo", info);
// 허용키, 제외키 설정
var info = {Type:"Text",AcceptKeys:"N|[abcd!@#]", ExceptKeys:"[890!]"};
mySheet.InitCellProperty(3, 4 ,info);
```

- **제공 버전**

|  **7.0.0.0**   |                                                     |
|:--------------:|-----------------------------------------------------|
|  **7.0.7.2**   | 팝업버튼 사용여부 설정을 위한 PopupButton 속성 추가 |
|  **7.0.12.3**  | ItemCode, ItemText, MaxCheck 속성 추가              |
| **7.0.13.12**  | RadioIcon 속성 추가                                 |
| **7.0.13.24**  | EmptyToReplaceChar, ZeroToReplaceChar 속성 추가     |
| **7.0.13.125** | ComboDisabled 속성 추가.                            |