# InitColumns Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > InitColumns Method

---

- **기능**

> 각 컬럼의 데이터 타입, 포맷 및 기능들을 설정한다..

- **Syntax**

|        |                                       |
|:------:|---------------------------------------|
| Syntax | ObjId.**InitColumns**(Cols, DataRow); |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                                                             |
| --------- | ------ | ---- | --------------------------------------------------------------- |
| Cols      | Object | 필수   | 각 컬럼의 기능을 json 형태로 설정한다.                                        |
| DataRow   | Number | 선택   | 단위데이터행 개수 단위데이터행 구조를 사용하는 경우 해당 인자의 값과 Cols 인자의 배열 길이가 동일해야 한다. |

- **세부내용**

> 컬럼 별로 설정 할 수 있는 속성은 다음과 같다.
>
> *※ 컬럼별 설정이 가능한 속성여부는 [Appendix#1.컬럼 타입별 정의 가능한 속성](#_1._컬럼_타입별) 참조*

| 속성                 | 타입               | 설명                                                                                                                                                                                                                                                                                                                                                                 |
| ------------------ | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Type               | String           | 컬럼의 데이터 타입 (필수)                                                                                                                                                                                                                                                                                                                                                    |
| AcceptKeys         | String           | 입력허용키 설정 "N" : 숫자만 허용 "E" : 영문만 허용 “K” : 한글만 허용 "N\|E" : 숫자, 영문만 허용 “N\|E\|K” : 숫자, 영문, 한글만 허용 "N\|E\|[사용자정의문자]" : 숫자, 영문과 사용자정의문자로 설정한 문자 허용 예) "N\|[abc!]" 설정 시 숫자와 a, b, c, ! 문자만 입력 가능 사용자 정의 문자열은 꼭 대괄호로 묶어서 설정해야 하며 사용자정의문자와 숫자, 영문 설정문자의 합집합으로 처리된다. 한글키는 오직 모던브라우저와 IE9 이상에서 사용 가능. AcceptKeys 와 ExceptKeys를 둘다 설정하고 설정키 내에 동일 문자가 있는 경우 해당 문자는 입력불가 처리된다. |
| ActionMenu         | Object[]         | 컨텍스트 메뉴                                                                                                                                                                                                                                                                                                                                                            |
| Align              | String           | 데이터의 정렬                                                                                                                                                                                                                                                                                                                                                            |
| AllowNull          | Boolean          | 숫자계열 컬럼에 빈값 허용 여부 설정                                                                                                                                                                                                                                                                                                                                               |
| ApproximateType    | Number           | 근사값처리방식 (1:반올림, 2:내림, 3:올림)                                                                                                                                                                                                                                                                                                                                        |
| AutoSum            | Boolean          | 타입과 무관하게 합계행 사용 가능 여부 (SumType 속성과 함께 사용)                                                                                                                                                                                                                                                                                                                          |
| BackColor          | String           | 배경 색상                                                                                                                                                                                                                                                                                                                                                              |
| ButtonUrl          | String/Number    | 팝업 버튼의 이미지 경로 또는 이미지리스트의 Index                                                                                                                                                                                                                                                                                                                                     |
| CalcLogic          | String / Object  | 컬럼별 계산식 문자열 또는 설정 객체                                                                                                                                                                                                                                                                                                                                               |
| CaseSensitive      | Boolean          | 필터링시 대소구분 처리 여부 (Default=1)                                                                                                                                                                                                                                                                                                                                        |
| Chart              | Object           | 스파크라인 차트 타입에 대한 세부 속성 설정                                                                                                                                                                                                                                                                                                                                           |
| CheckSaveName      | String           | 트리기준컬럼의 체크박스에 대한 SaveName                                                                                                                                                                                                                                                                                                                                          |
| ClassName          | String           | 버튼의 사용자정의 클래스 postfix 명                                                                                                                                                                                                                                                                                                                                            |
| ColMerge           | Number           | 컬럼의 셀 병합 처리 방법                                                                                                                                                                                                                                                                                                                                                     |
| ColSpan            | Number           | ColSpan 범위 값 (단위데이터행 구조에서만 사용 가능)                                                                                                                                                                                                                                                                                                                                  |
| ComboCode          | String           | 콤보 리스트의 코드 집합                                                                                                                                                                                                                                                                                                                                                      |
| ComboDisabled      | String           | 콤보 리스트의 선택 불가능한 item 설정.                                                                                                                                                                                                                                                                                                                                           |
| ComboFilter        | Number           | ComboEdit 컬럼 타입의 필터링 처리 모드 설정                                                                                                                                                                                                                                                                                                                                      |
| ComboText          | String           | 콤보 리스트의 문자열 집합                                                                                                                                                                                                                                                                                                                                                     |
| CopyPaste          | Boolean / String | 컬럼의 복사 기능 제어 (Default = 1, 복사 허용)                                                                                                                                                                                                                                                                                                                                  |
| Cursor             | String           | 마우스 모양 설정                                                                                                                                                                                                                                                                                                                                                          |
| CustomDate         | Boolean          | 사용자 정의 날짜 사용여부                                                                                                                                                                                                                                                                                                                                                     |
| DefaultValue       | String           | 신규입력시 기본값 설정                                                                                                                                                                                                                                                                                                                                                       |
| DecimalAdjust      | Number           | Int 타입 조회 시 원본 값 처리 방식 설정. (Default:2) \| 설정값 \| 설명               \| \| --- \| ---------------- \| \| 1   \| 원본값 반올림          \| \| 2   \| 원본값 내림 (Default) \| \| 3   \| 원본값 올림           \|                                                                                                                                                                       |
| Edit               | Boolean          | 편집가능 여부                                                                                                                                                                                                                                                                                                                                                            |
| EditLen            | Number           | 편집시 입력 최대 허용 길이                                                                                                                                                                                                                                                                                                                                                    |
| EditPointCount     | Number           | 편집시점에서의 소수점 자리수 입력제한 개수 설정                                                                                                                                                                                                                                                                                                                                         |
| Ellipsis           | Boolean          | 말줄임 여부                                                                                                                                                                                                                                                                                                                                                             |
| EmptyToReplaceChar | String           | 빈값인 경우 대체하여 보여줄 문자 설정                                                                                                                                                                                                                                                                                                                                              |
| EnterMode          | Boolean          | 다중라인 입력모드(MultiLineText)에서 Enter 키 입력에 대한 개행 처리 여부 (Default:0)                                                                                                                                                                                                                                                                                                     |
| ExceptKeys         | String           | 입력제외키 설정 "N" : 숫자 입력 불가 "E" : 영문 입력 불가 "N\|E" : 숫자, 영문 입력 불가 "N\|E\|[사용자정의문자]" : 숫자, 영문과 사용자정의문자로 설정한 문자 입력 불가 예) "N\|[abc!]" 설정 시 숫자와 a, b, c, ! 문자만 입력 불가 사용자 정의 문자열은 꼭 대괄호로 묶어서 설정해야 하며 사용자정의문자와 숫자,영문 설정문자의 합집합으로 처리된다. AcceptKeys 와 ExceptKeys를 둘다 설정하고 설정키 내에 동일 문자가 있는 경우 해당 문자는 입력불가 처리된다.                                                                 |
| ExcludeEmpty       | Boolean          | AutoSum 컬럽타입 및 소계행의 평균 또는 건수 계산시 빈값을 포함 할지 여부 (Default=0)                                                                                                                                                                                                                                                                                                          |
| FalseValue         | String           | 1 이외의 CheckBox 형태 컬럼의 False 값 지정. "F" 으로 지정한 경우 0 대신 "F"를 False 값으로 사용 가능.                                                                                                                                                                                                                                                                                         |
| FitColWidth        | Boolean          | FitColWidth 메소드 호출시 비율에 의한 너비 재조정 허용 여부 (Default=1)                                                                                                                                                                                                                                                                                                                |
| Focus              | Boolean          | 포커스 허용 여부                                                                                                                                                                                                                                                                                                                                                          |
| FontBold           | Boolean          | 폰트 굵기 여부                                                                                                                                                                                                                                                                                                                                                           |
| FontColor          | String           | 폰트 색상                                                                                                                                                                                                                                                                                                                                                              |
| FontUnderline      | Boolean          | 폰트 언더라인 여부                                                                                                                                                                                                                                                                                                                                                         |
| Format             | String / Array   | 데이터의 Mask 적용 형태                                                                                                                                                                                                                                                                                                                                                    |
| FormatFix          | Boolean          | GetCellValue 시 GetCellText 값을 반환 할지 여부 (Default=0) 특히 True 로 설정시 저장할 때 Format 이 설정된 상태로 저장한다.                                                                                                                                                                                                                                                                      |
| FullInput          | Boolean          | 컬럼타입이 단일행 문자열인 경우 전체길이(EditLen)만큼의 입력 여부                                                                                                                                                                                                                                                                                                                           |
| GroupSumType       | String           | 그룹핑 처리시 부모노드의 셀에 처리할 계산 방식 설정 (Default="") "Sum" : 합계계산 "Count" : 건수계산 “Avg” : 평균계산                                                                                                                                                                                                                                                                                |
| HeaderCheck        | Boolean          | 헤더에 전체 체크 표시 여부 (Default=1)                                                                                                                                                                                                                                                                                                                                        |
| Hidden             | Boolean          | 컬럼 숨김 여부                                                                                                                                                                                                                                                                                                                                                           |
| HoverUnderline     | Boolean          | 마우스오버시 언더라인 여부                                                                                                                                                                                                                                                                                                                                                     |
| Image              | String           | 이미지 표현시 Url                                                                                                                                                                                                                                                                                                                                                        |
| ImgAlign           | String           | 이미지의 정렬                                                                                                                                                                                                                                                                                                                                                            |
| ImgHeight          | Number           | 이미지 높이                                                                                                                                                                                                                                                                                                                                                             |
| ImgWidth           | Number           | 이미지 너비                                                                                                                                                                                                                                                                                                                                                             |
| InputCaseSensitive | Number           | 입력시 영문에 대한 대소구문 자동 치환 처리에 대한 설정 0 : 별도 처리 하지 않음 (기본값) 1 : 대문자로 치환 2 : 소문자로 치환                                                                                                                                                                                                                                                                                      |
| InsertEdit         | Boolean          | 트랜잭션이 "입력"인 상태에서 데이터의 Edit 가능 여부                                                                                                                                                                                                                                                                                                                                   |
| ItemCode           | String           | 멀티체크 아이템의 코드를 구분자 "\|"로 연결한 문자열                                                                                                                                                                                                                                                                                                                                    |
| ItemText           | String           | 멀티체크 아이템의 텍스트를 구분자 "\|"로 연결한 문자열                                                                                                                                                                                                                                                                                                                                   |
| KeyField           | Boolean          | 필수 입력 항목                                                                                                                                                                                                                                                                                                                                                           |
| LevelSaveName      | String           | 트리 저장시 레벨값을 전달하기 위해서 사용하는 변수명                                                                                                                                                                                                                                                                                                                                      |
| MaxCheck           | Number           | 멀티체크의 최대 선택 개수 설정 (Default : 0)                                                                                                                                                                                                                                                                                                                                    |
| MaximumValue       | Number           | 숫자포맷일 때 편집시 입력할수 있는 최대값                                                                                                                                                                                                                                                                                                                                            |
| MenuFilter         | String           | Filter에서 사용할 옵션(여러개 선택시 '\|' 구분자로 연결)                                                                                                                                                                                                                                                                                                                              |
| MinimumValue       | Number           | 숫자포맷일 때 편집시 입력할수 있는 최소값                                                                                                                                                                                                                                                                                                                                            |
| MinWidth           | Number           | 컬럼 최소 가로크기                                                                                                                                                                                                                                                                                                                                                         |
| MultiLineText      | Boolean          | 다중라인 입력여부                                                                                                                                                                                                                                                                                                                                                          |
| NumberSort         | Boolean          | 숫자형 Sort 처리 사용 여부                                                                                                                                                                                                                                                                                                                                                  |
| PhoneMask          | Object           | Format이 PhoneNo 일 때 전화번호포맷에서 원하는 위치에 마스킹 설정.                                                                                                                                                                                                                                                                                                                       |
| PointCount         | Number           | 컬럼타입이 Float 인 경우 소수점 이하의 자리수                                                                                                                                                                                                                                                                                                                                       |
| PopupButton        | Boolean          | 팝업버튼 사용 여부                                                                                                                                                                                                                                                                                                                                                         |
| PopupCheckEdit     | Boolean          | 팝업메뉴 설정시 편집가능 여부                                                                                                                                                                                                                                                                                                                                                   |
| PopupCode          | String           | 팝업메뉴의 코드 집합                                                                                                                                                                                                                                                                                                                                                        |
| PopupText          | String           | 팝업메뉴의 문자열 집합                                                                                                                                                                                                                                                                                                                                                       |
| RadioIcon          | Boolean          | 데이터 셀내의 체크박스 계열의 이미지 모양 설정                                                                                                                                                                                                                                                                                                                                         |
| RowMerge           | Boolean          | 대상 컬럼의 RowMerge 허용 여부 (Default=1)                                                                                                                                                                                                                                                                                                                                  |
| RowSpan            | Number           | RowSpan 범위 값 (단위데이터행 구조에서만 사용 가능)                                                                                                                                                                                                                                                                                                                                  |
| Save               | Boolean          | 저장 또는 저장관련 메소드에서 해당 컬럼의 값 포함 여부 (Default=1)                                                                                                                                                                                                                                                                                                                        |
| SaveName           | String           | 데이터 저장 또는 조회시 사용하는 변수명                                                                                                                                                                                                                                                                                                                                             |
| ShowCol            | Number           | 멀티콤보 설정 시 컬럼 값으로 출력할 컬럼 설정                                                                                                                                                                                                                                                                                                                                         |
| Sort               | Boolean          | 헤더 클릭시 소트 가능 여부 (Default=1)                                                                                                                                                                                                                                                                                                                                        |
| StaticPassword     | Boolean          | 값이 0인 경우 데이터 길이만큼 ‘*’ 의 수를 표현한다.                                                                                                                                                                                                                                                                                                                                   |
| SumType            | String           | 합계 계산 방식 설정 (Default="Sum")                                                                                                                                                                                                                                                                                                                                        |
| ToolTip            | Boolean/String   | 셀의 풍선도움말 표시 여부 또는 설정할 문자열                                                                                                                                                                                                                                                                                                                                          |
| ToolTipText        | String           | 헤더행의 풍선 도움말에 설정할 문자열                                                                                                                                                                                                                                                                                                                                               |
| Transaction        | Boolean          | 트랜잭션 허용 여부 (Default=1)                                                                                                                                                                                                                                                                                                                                             |
| TreeCheck          | Boolean          | 트리 기준컬럼에서 체크박스 사용여부                                                                                                                                                                                                                                                                                                                                                |
| TreeCol            | Boolean          | 트리 기준컬럼                                                                                                                                                                                                                                                                                                                                                            |
| TrueValue          | String           | 1 이외의 CheckBox 형태 컬럼의 True 값 지정. "M" 으로 지정한 경우 1 대신 "M"을 True 값으로 사용 가능.                                                                                                                                                                                                                                                                                           |
| UpdateEdit         | Boolean          | 트랜잭션이 "조회"인 상태에서 데이터의 Edit 가능 여부                                                                                                                                                                                                                                                                                                                                   |
| VAlign             | String           | 컬럼 상/하 정렬 (Default="middle")                                                                                                                                                                                                                                                                                                                                       |
| Validation         | Boolean          | 콤보에디트 컬럼 유효성 검사 사용여부 설정 (Default=0)                                                                                                                                                                                                                                                                                                                                |
| Width              | Number           | 컬럼의 너비                                                                                                                                                                                                                                                                                                                                                             |
| Wrap               | Boolean          | 자동 줄바꿈 여부                                                                                                                                                                                                                                                                                                                                                          |
| ZeroToReplaceChar  | String           | 값이 0인 경우 대체하여 보여줄 문자 설정                                                                                                                                                                                                                                                                                                                                            |

> **Type**은 해당 컬럼에 대한 Type 설정으로 다음과 같은 값을 설정 할 수 있다.

| Type       | 설명                                                                               |
| ---------- | -------------------------------------------------------------------------------- |
| Text       | 기본 문자열 데이터 타입                                                                    |
| Status     | 행에 대한 트랜잭션 상태를 표현하는 데이터 타입                                                       |
| DelCheck   | 행에 대한 삭제여부를 설정하는 CheckBox 형태 데이터 타입                                              |
| CheckBox   | CheckBox 데이터 타입                                                                  |
| DummyCheck | 이벤트를 발생하지 않는 CheckBox 데이터 타입                                                     |
| Radio      | 데이터 행 중 하나의 데이터만 선택하는 Radio 데이터 타입                                               |
| Combo      | DropDown 리스트 데이터 타입                                                              |
| ComboEdit  | 편집 및 필터링이 가능한 DropDown 리스트 데이터 타입 (모바일지원안함)                                      |
| AutoSum    | 합계행에 합계를 표현하는 숫자형 데이터 타입으로, 포맷이 “Integer”, “#,###”, “#,##0” 등의 경우에 한해 소수점 자리를 버림 |
| Image      | 이미지 형태의 데이터 타입                                                                   |
| Int        | 정수형 숫자 데이터 타입으로, 값이 실수인 경우 소수점 자리를 버림                                            |
| Float      | 실수형 숫자 데이터 타입                                                                    |
| Date       | 날짜 데이터 타입                                                                        |
| Popup      | 우측에 팝업 버튼을 갖는 읽기 전용 문자열 데이터 타입                                                   |
| Pass       | Password 데이터 타입                                                                  |
| Seq        | 행의 생성 순서값을 표현하는 데이터 타입                                                           |
| Html       | Html 태그형태를 표현하는 데이터 타입                                                           |
| Result     | 저장 처리 결과를 표시하는 데이터 타입                                                            |
| Sparkline  | 스파크라인 차트를 표현하는 데이터 타입                                                            |
| Button     | 버튼 형태를 표현하는 데이터 타입                                                               |

> **※ 모바일에서는 ComboEdit 타입은 Combo 타입으로 대체되어 표현된다.**
>
> **Align**은 데이터에 대한 정렬 설정 Left, Center, Right 값을 설정한다.

| DataAlign | 설명                      |
|:---------:|---------------------------|
|   Left    | 좌측 정렬 데이터(Default) |
|  Center   | 가운데 정렬 데이터        |
|   Right   | 우측 정렬 데이터          |

> **AcceptKeys**는 컬럼의 입력허용키를 설정한다.
>
> "N" : 숫자만 허용
>
> "E" : 영문만 허용
>
> “K” : 한글만 허용
>
> "N\|E" : 숫자, 영문만 허용
>
> "N\|E\|[사용자정의문자]" : 숫자, 영문과 사용자정의문자로 설정한 문자 허용
>
> 예) "N\|[abc!]" 설정 시 숫자와 a, b, c, ! 문자만 입력 가능
>
> 사용자 정의 문자열은 꼭 대괄호로 묶어서 설정해야 하며 사용자정의문자와 숫자,영문 설정문자의 합집합으로 처리된다.
>
> AcceptKeys 와 ExceptKeys를 둘다 설정하고 설정키 내에 동일 문자가 있는 경우 해당 문자는 입력불가 처리된다.
>
> **ActionMenu**는 컬럼의 컨텍스트 메뉴를 설정하는 속성이다. 항목의 Text, Code, Icon 을 갖는 객체의 배열로 설정을 기본으로 하며, 약식 설정 방법인 항목의 Text 배열로 설정 할 수 있다. 항목의 Code 속성을 설정하지 않거나, 약식 방법으로 설정하는 경우 Code는 Text 설정값과 동일한 값으로 설정 된다. 메뉴 선택시 OnSelectMenu 이벤트를 발생하고, 시트의 ActionMenu와 같이 사용시 컬럼의 ActionMenu 설정이 우선적으로 처리된다.
>
> 설정 방법은 아래와 같다.

```javascript
// 일반 설정
var actionMenu = [
{‘Text':'메뉴01', Code:'01'}, {‘Text':'메뉴02', Code:'02'}, {‘Text':'메뉴02', Code:'03'}
];
// 일반 설정 : Code 생략
var actionMenu = [
{‘Text':'메뉴01'}, {‘Text':'메뉴02'}, {‘Text':'메뉴02'}
];
// 약식 설정
var actionMenu = [‘메뉴01', ‘메뉴02', ‘메뉴03'];
```

> **AutoSum**은 타입과 무관하게 합계행을 사용할 수 있도록 설정 한다(SumType과 함께 사용).
>
> **BackColor**는 컬럼의 배경색상을 설정 한다.
>
> **ButtonUrl**은 컬럼타입이 Popup일 때 표시되는 팝업 버튼의 이미지를 변경하고자 할 때 사용하는 속성 이다. 이 속성을 설정하지 않은 경우 기본적으로 테마의 "popup.gif" 이미지를 표시 하고, 날짜 포맷을 설정한 경우 "calendar.gif" 이미지를 표시 한다. 별도의 이미지를 사용하고자 하는 경우에 이 속성을 이용하여 설정 한다. 설정 값은 설정하고자 하는 이미지의 경로 문자열 또는 이미지리스트의 Index값으로 설정 하며, 설정 시 설정된 테마의 경로를 기준으로 설정하여야 한다. 이미지의 사이즈는 12\*12 로 사용해야 올바르게 표현이 된다. 동적 변경이 아닌 경우에는 테마의 해당 이미지를 교체하여 사용하는 것을 권장 한다.
>
> **CalcLogic** 속성은 행 내의 컬럼간 계산식을 설정할 때 사용하는 속성이다. 설정 방법은 문자열 형식의 설정 방법과 함수 형식의 설정 방법이 있다.
>
> 문자열 형식의 설정은 컬럼의 값을 사용하여 사칙연산의 간단한 계산식을 설정하는 경우에 사용하며, 계산식에 컬럼을 포함하는 경우 해당 컬럼의 Index 또는 SaveName을 기호 "\|"로 감싸서 표현 한다. 사용 예제는 아래와 같다.

```
// SaveName이 "sBase"인 컬럼과 Index가 3인 컬럼의 합을 이용한 계산
"CalcLogic" : "(|sBase| + |3|) * 2"
```

> 함수 형식의 설정은 아래와 같이 세부 속성을 설정 한다.

|  |  |  |  |
|:--:|:--:|:--:|:--:|
| Parameter | Type | 필수여부 | 설 명 |
| TriggerCols | String | 선택 | 대상 컬럼의 Index 또는 SaveName 을 구분자 "\|"로 연결한 문자열 |
| Function | Function | 필수 | 계산식 처리 함수 |

> Function 속성은 계산식 처리시 호출할 함수를 설정하며, 익명 또는 전역함수를 설정 할 수 있다. 함수 호출시 전달되는 인자는 아래와 같다.

|           |        |                   |
|:---------:|:------:|:-----------------:|
| Parameter |  Type  |       설 명       |
|   Shet    | Object |  대상 시트 객체   |
|    Row    | Number |  대상 행의 Index  |
|    Col    | Number | 대상 컬럼의 Index |

> TriggerCols 속성을 설정하지 않은 경우 대상행의 컬럼의 데이터가 변경시 계산식 함수가 호출 되고, 특정 컬럼이 변경된 경우에만 계산식 함수를 호출 하는 경우 해당 컬럼을 TriggerCols에 설정 한다. 일반적으로 계산식 함수에서 사용하는 컬럼들의 정의하여 사용 한다. 사용예제는 아래와 같다.

```javascript
// 익명함수 사용 방법
"CalcLogic": {
"TriggerCols": "sBase",
"Function": function(info) {
var res = info.Sheet.GetCellValue(info.Row, "sBase") * 2;
return res;
}
}
// 전역 함수 사용 방법 (별도 정의)
function fnCalcSample(info) {
var res = info.Sheet.GetCellValue(info.Row, "sBase") * 2;
return res;
}
"CalcLogic": {
"TriggerCols": "sBase",
"Function": fnCalcSample
}
```

> *※ 계산식 함수는 모든 행에 대해서 대상컬럼이 변경되는 시점마다 호출되기 때문에 복잡한 로직을 사용하는 경우 성능 저하의 원인이 될 수 있습니다.*
>
> **CaseSensitive**는 필터링 처리시 영문의 대소구분 처리 여부를 설정한다.
>
> **Chart**는 스파크라인 컬럼 타입 사용시 차트에 대한 세부 속성을 설정 한다.
>
> 이 속성은 스파크라인 컬럼 타입에서만 유효하며 세부 속성은 다음과 같다.

| Parameter     | Type   | 필수여부 | 설 명                                                                                                                                                                                                                            |
| ------------- | ------ | ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Type          | String | 선택   | 스파크라인 차트의 타입 \| 설정값     \| 설명                \| \| ------- \| ----------------- \| \| Area    \| Area 차트 (Default) \| \| Line    \| Line 차트           \| \| Column  \| Column 차트         \| \| WinLose \| 승-패 차트            \| |
| Data          | String | 필수   | 차트를 구성할 컬럼의 Index 또는 SaveName을 구분자 "\|"로 연결한 문자열                                                                                                                                                                               |
| Color         | String | 선택   | 양수 값(영역)에 대한 색상 값 (Default="#4f81bd")                                                                                                                                                                                          |
| NeagtiveColor | String | 선택   | 음수 값(영역)대 대한 색상 값 (Default="#c0504d")                                                                                                                                                                                          |

> 스파크라인 차트 사용시 ibchart.js 를 인클루드해야 사용 할수 있으며 IE 브라우저는 9이상에서만 지원 한다. (타 브라우저는 모두 지원)
>
> Ibcharts.js 를 인클루드 하지 않거나 지원하지 않는 브라우저에서는 차트가 표현되지 않고 빈 여백으로 표시 된다.
>
> **CheckSaveName**은 트리구조에서 트리 기준컬럼에 체크박스를 사용시 체크박스의 값을 서버에 전달시 사용할 SaveName을 설정한다. 해당 SaveName이 설정되어 있는 경우에만 저장 관련 메소드 호출시 해당 체크값을 수집하게 된다. 이 속성은 해당 컬럼에 TreeCol, TreeCheck 가 모두 true로 설정되어 있는 경우에만 유효하다.
>
> **ClassName**은 "Button" 컬럼타입의 버튼에 대한 사용자정의 클래스를 적용하고자 하는 경우 사용한다. 이 속성을 설정하지 않는 경우 기본 클래스로 적용된고, 설정 시 기본 Class의 Postfix로 적용된다. 메인테마 기준 기본 Class 및 속성 설정에 대한 Class는 아래와 같다.

| 구분                   | 기본 Class 명       | "Red"로 설정한 Class 명    |
|------------------------|---------------------|----------------------------|
| 기본 스타일            | GMCellButtonBase    | GMCellButtonBase**Red**    |
| 활성화 상태의 스타일   | GMCellButton        | GMCellButton**Red**        |
| 비활성화 상태의 스타일 | GMCellButton0       | GMCellButton**Red**0       |
| 활성화의 Hover         | GMCellButton:hover  | GMCellButton**Red**:hover  |
| 비활성화의 Hover       | GMCellButton0:hover | GMCellButton**Red**0:hover |

> 해당 css Class는 반드시 해당 테마의 ibsheet.css 에 정의되어야 한다.
>
> **CopyPaste**는 해당 컬럼에 대한 복사/붙여넣기 기능얼 제어하는 속성이다.

| 설정값 | 설명                               |
|:------:|------------------------------------|
|   0    | 컬럼 복사/붙여넣기 허용안됨.       |
|   1    | 컬럼 복사/붙여넣기 허용. (Default) |

> **ColMerge**는 데이터 컬럼에 대한 세로 머지 처리방법을 설정한다. 설정할 수기본적으있는 값은아래와 같으며, 설정이 없는 경우는 기본값 1로 처리 한다.

| 설정값 | 설명                          |
|:------:|-------------------------------|
|   0    | 셀 병합 사용 안함             |
|   1    | 셀 병합 사용 함               |
|   2    | 가상 셀 병합 방법으로 사용 함 |

> 셀병합은 기본적으로 table의 colspan, rowspan 속성을 이용하기 때문에, 범위가 큰 경우 대상 행을 모두 랜더링을 해야하는 문제로 성능이 저하 될 수 있다. 이런 경우 설정 값 2로 사용하면 실제 셀병합을 하지 않고, 가상으로 처리하는 방법을 사용하기 때문에 성능을 향상 시킬 수 있다.
>
> **ColSpan**은 단위 데이터 행 구조에서 단위 데이터 행 범위 내에서 고정으로 적용 할 ColSpan 범위를 설정 한다. 이 속성 설정시 데이터의 동일 유무와 관계없이 셀 병합 처리를 하여 표현 된다. 이 속성은 단위 데이터 행 구조에서 만 유효하며, 해당 속성을 사용하기 위해서는 MergeSheet 설정값을 3 또는 8로 설정 하여야 한다. (연관 속성 : RowSpan)
>
> **ComboCode**는 Type이 "Combo" 또는 "ComboEdit"인 경우 저장될 코드 항목을 "\|"로 연결하여 구성하며 위의 ComboText 항목의 개수와 동일 하여야 한다.
>
> **ComboDisabled**는 Type이 "Combo" 인 경우 선택 불가능한 item을 설정한다.
>
> 설정값이 1인경우 선택 불가, 0인 경우에는 선택 가능 item 이다
>
> ComboCode의 개수만큼 설정하며 "\|"로 연결하여 구성한다.
>
> 예) ComboDisabled : “1\|0\|0” -> 첫번째 항목 선택 불가로 설정.
>
> **ComboFilter**는 Type이 "ComboEdit"인 경우 목록에 대한 필터링 처리 방법을 설정 한다. 설정값에 따른 처리는 다음과 같다.

| ComboFilter | 설명                              |
|:-----------:|-----------------------------------|
|      0      | 필터 기능 사용 안함               |
|      1      | 특정 부분 일치 형태의 필터링 모드 |
|      2      | 앞문자열 일치 형태의 필터링 모드  |

> **ComboText**는 Type이 "Combo" 또는 "ComboEdit"인 경우 화면에 보여질 문자열 항목을 "\|"로 연결하여 구성한다.
>
> 콤보리스트를 다중 컬럼 형태로 출력하려면 문자열을 "\t"로 연결하여 구성한다.
>
> 예) ComboText:"가\t나\t다\|라\t마\t바"
>
> **Cursor는** 해당 컬럼에 마우스 오버 시 커서의 모양을 설정한다.
>
> "Default","Pointer" 로 설정이 가능하며 기본적으로 "Default"값이 설정된다.
>
> DefaultValue는 신규입력시 기본값을 설정한다. 기본적으로 ""이 설정된다.
>
> **Edit**는 데이터의 편집가능 여부를 설정한다. 기본적으로 1이 설정된다.
>
> **EditLen**는 데이터의 입력 가능한 최대 글자 수를 설정한다.
>
> **EditPointCount**는 실수 형태의 포맷에서, 편집시 소수점 자리 수에 대한 입력제한 개수를 설정 한다. 이 속성은 편집시에 대해서만 유효하다.
>
> **Ellipsis**는 컬럼 텍스트의 표시글자가 잘릴 경우 말 줄임 여부를 설정한다. 기본적으로 0값이 설정된다
>
> **EmptyToReplaceChar**는 데이터 타입이 "Int", "Float", "AutoSum"이고, 해당 셀의 값이 빈값일 때, 화면에 빈 값을 대체하여 표시할 문자 또는 문자열을 설정하는 기능이다. 화면 표시에만 해당 설정한 문자열로 보여지게 되고, 내부에서 처리되는 값는 빈값으로 처리되기 때문에 저장 또는 문서 연동시에는 해당 설정값으로 처리되지 않는다.
>
> **EnterMode**는 다중라인 입력모드(MultiLineText)에서 Enter 키 입력에 대한 개행 처리 여부를 설정 한다. 이 속성은 MultiLineText 속성이 1(true)인 경우에만 유효하며, EditEnterBehavior 메소드 설정보다 우선 처리 된다.
>
> **ExceptKeys**는 컬럼의 입력제외키를 설정한다.
>
> "N" : 숫자 입력 불가
>
> "E" : 영문 입력 불가
>
> "N\|E" : 숫자, 영문 입력 불가
>
> "N\|E\|[사용자정의문자]" : 숫자, 영문과 사용자정의문자로 설정한 문자 입력 불가
>
> 예) "N\|[abc!]" 설정 시 숫자와 a, b, c, ! 문자만 입력 불가
>
> 사용자 정의 문자열은 꼭 대괄호로 묶어서 설정해야 하며 사용자정의문자와 숫자,영문 설정문자의 합집합으로 처리된다.
>
> AcceptKeys 와 ExceptKeys를 둘다 설정하고 설정키 내에 동일 문자가 있는 경우 해당 문자는 입력불가 처리된다.
>
> **ExcludeEmpty**는 AutoSum 컬럼 타입 혹은 소계행인 경우 빈 값을 평균 또는 건수 계산시 포함할지 여부를 설정 한다. 설정 하지 않는 경우는 기본적으로 0값이 설정(포함하여 계산)된다. 단, 포맷을 지정하지 않거나 NullInteger 또는 NullFloat 의 포맷만 사용가능.
>
> **FitColWidth**는 FitColWidth 메소드 호출시 현재의 컬럼 너비 비율에 맞개 너비를 재조정 처리를 허용할지 여부를 설정한다. 설정값이 1인 경우는 컬럼의 너비 비율에 맞게 너비가 재조정되며, 설정값이 0인 경우는 현재의 컬럼 너비를 그대로 유지 한다. 이 속성은 FitColWidth 메소드의 인자를 설정하지 않고 호출하는 경우에만 적용된다.
>
> **FontColor**는 컬럼의 폰트색상을 설정한다.
>
> **Format**은 데이터에 대한 Mask 적용 형태를 설정하는 것으로 다음과 같은 값을 설정한다. 포맷 설정은 기본제공 외에 사용자가 직접 정의 해서 설정 할 수 있으며 ((ex) Format="#,###,#0") Type 값에 따라 설정한 Format이 적용 된다.

| Format      | 설명                                         | 사용가능타입                |
| ----------- | ------------------------------------------ | --------------------- |
| Ymd         | "년월일" 형태. Ibmsg의 SYS_d 포맷을 따른다             | Date,Text,Popup       |
| Ym          | "년월" 형태, ibmsg의 SYS_m 포맷을 따른다.             | Date,Text,Popup       |
| Md          | "월일" 형태. Ibmsg의 SYS_M 포맷을 따른다.             | Date,Text,Popup       |
| Hms         | "시분초" 형태. Ibmsg의 SYS_T 포맷을 따른다.            | Date,Text,Popup       |
| Hm          | "시분" 형태. Ibmsg의 SYS_t 포맷을 따른다.             | Date,Text,Popup       |
| YmdHms      | "년월일시분초" 형태. Ibmsg의 SYS_G 포맷을 따른다          | Date,Text,Popup       |
| YmdHm       | "년월일시분" 형태. Ibmsg의 SYS_g 포맷을 따른다           | Date,Text,Popup       |
| Integer     | 정수 형태, 기본 0 DefaultFormat : #,##0.         | Int,AutoSum,AutoAvg   |
| NullInteger | 널 정수 형태, 기본 널 DefaultFormat : #,###.###### | Int,AutoSum,AutoAvg   |
| Float       | 실수 형태, 기본 0 DefaultFormat : #,##0.######   | Float,AutoSum,AutoAvg |
| NullFloat   | 널 실수 형태, 기본 널 DefaultFormat : #,###.###### | Float,AutoSum,AutoAvg |
| IdNo        | 주민등록번호 형태                                  | Text                  |
| SaupNo      | 사업자번호 형태                                   | Text                  |
| PostNo      | 우편번호 형태 (6자리, 5자리 지원)                      | Text                  |
| CardNo      | 카드번호 형태                                    | Text                  |
| PhoneNo     | 전화번호 형태                                    | Text                  |
| Number      | 숫자 형태 (특정 포맷없이 숫자키만 입력 받는 형태)              | Text                  |

> **※ 사용자 숫자 포맷 가이드**
>
> "#", "0", "," "." 조합으로 기본제공 포맷 이외의 포맷을 정의하여 사용 할 수 있다. 사용가능한 타입은 Int, Float, AutoSum, AutoAvg 타입이다.
>
> 사용방법은 아래 표와 같다.

| 구분                  | 기호  | 설명                                                                                                                                                                                                                           |
| ------------------- | --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 숫자                  | #   | 해당위치에 값이 있는 경우 해당 값을 표시하고, 없는 경우는 빈값으로 표시한다. 소수점 이하에서 사용하는 경우는 표시할 자리수를 결정하며 입력된 값의 자리수가 #의 개수보다 많은 경우 반올림하여 개수만큼 표시한다. 예) Input= 12345.678, Format=#,###.##,Output=12,345.68 Input= 0.789 Format=#,###.##,Output=.79        |
| 숫자                  | 0   | 해당위치에 값이 있는 경우 해당 값을 표시하고, 없는 경우는 0으로 표시한다. 소수점 이하에서 "#"과 동일하게 동작한다. 예) Input=123456.7 Format=#,##0.00 Result=123,456.70 Input= 0.7 Format=#,##0.00 Result=0.70                                                              |
| 소수점                 | .   | 소수점이 있는 경우 실수표현이 가능하며 소수점을 표현하는 경우 ibmsg의 SYS_DecimalSeparator에 설정되어 있는 값으로 표현된다.                                                                                                                                            |
| 천단위구분자              | ,   | 천단위 구분자를 넣은 경우 천단위 마다 구분자를 표시하며 ibmsg 의 SYS_GroupSeparator에 설정되어 있는 값으로 표현된다. 또한, 소수점 바로 앞에 사용하는 경우는 콤마 개수만큼 1000으로 나눈 값으로 표현한다. 예) Input= 123456.789 Format=0,.00 Result=123.46 Input= 123456.789 Format=0,,.00 Result=0.12 |
| 퍼센트                 | \\% | 마지막에 퍼센트 기호를 넣는 경우 자동으로 %를 표현한다. 예) Input=123.456 Format=#,##0.00\\% Result=123.46%                                                                                                                                          |
| Indian Numbering 표현 |     | Indian Numbering 포맷은 1,00,00,000 과 같이 천단위 구분자 이상에서는 두자리 마다 구분자를 넣는 방식을 사용한다. 이와 같은 포맷 설정시 "#,##,###" 와 같이 설정하여 사용 할 수 있다. 예) Input=123456 Format=#,##,### Result=1,23,456 Input=12345678 Format=#,##,### Result=1,23,45,678  |

> **※ 사용자 문자 포맷 가이드**
>
> "#", "\*", 그외 조합으로 기본제공 포맷 이외의 포맷을 정의 하여 사용 할 수 있다. 사용가능한 타입은 Text타입이다.
>
> 사용방법은 아래 표와 같다.

| 구분  | 기호  | 설명                                                                                                                |
| --- | --- | ----------------------------------------------------------------------------------------------------------------- |
| 문자  | #   | 해당위치에 값이 있는 경우 해당 값을 표시하고, 없는 경우는 빈값으로 표시한다. 예) Input=7907211022553, Format=######-****###, Result=790721-****553 |
| 문자  | *   | 해당위치에 값이 있는 경우 해당 값을 표시하고, 없는 경우는 빈값으로 표시한다. 예) Input=7907211022553, Format=######-****###, Result=790721-****553 |
| 문자  | 그외  | #,*이외의 문자 숫자에 대해선 그대로 표시한다.                                                                                       |

> **※ "Text", "Popup" 컬럼 타입에서의 다중 포맷 가이드**
>
> 한 컬럼내에 2개 이상의 포맷을 설정하고자 하는 경우 Format 속성에 해당하는 포맷 문자열을 배열 형식으로 설정한다. 이와 같이 설정하는 경우 입력된 문자열의 길이에 따라 해당 길이와 일치하는 포맷 문자열이 적용되며, 일치하는 포맷 문자열이 없는 경우 가장 첫번째 설정한 포맷 문자열을 기준으로 설정 된다.
>
> 편집 시 문자열 입력 길이와 같이 적용 포맷이 명확하지 않는 경우 배열의 가장 첫번째 설정한 포맷 기준으로 처리 되므로, 길이가 가장 긴 포맷을 첫번째에 설정을 권장한다.
>
> (예) 주민번호, 사업자번호 포맷 설정 : Format : ["IdNo", "SaupNo"]  
> "1234567890123" 🡪 "123456-7890123" : "IdNo" 적용
>
> "1234567890" 🡪 "123-45-67890" : "SaupNo" 적용
>
> "1234567" 🡪 "123456-7" : "IdNo" 적용
>
> **FormatFix**는 GetCellValue 시 GetCellText 값을 반환 할지 여부를 설정한다. 특히 True 로 설정시 저장할 때 Format 이 설정된 상태로 저장한다.
>
> 기본걱으로 0값이 설정된다.
>
> **FullInput**은 컬럼타입이 단일 행 문자열인 경우 EditLen 만큼 모두 입력해야 하는 경우 설정한다. 기본적으로 0값이 설정된다.
>
> **GroupSumType**은 그룹행 설정에 의한 데이터 구성시 부모행에 표현할 계산 방식을 설정한다. 합계 또는 건수 계산시 모든 자식행을 포함하여 계산한다.
>
> 이 속성은 ShowGroupRow 메소드를 통한 그룹행 사용시에만 유효한 속성이다. 설정값은 대소구분없이 설정이 가능하며, 설정할 수 있는 값은 아래와 같다.

| 설정값  | 설명                          |
|:-------:|-------------------------------|
|   ""    | 별도 계산 처리 없음 (Default) |
|  "Sum"  | 합계 계산 처리                |
| "Count" | 건수 계산 처리                |

> **HeaderCheck**는 컬럼에 헤더의 전체체크 표시 여부를 설정한다.
>
> 기본적으로 1값이 설정된다.
>
> **Hidden**은 데이터 컬럼 숨김 여부를 설정한다.
>
> **HoverUnderline**은 마우스 오버 시 셀 값에 언더라인 처리 여부를 설정한다. 기본적으로 0값이 설정된다.
>
> **Image**는 컬럼에 이미지를 같이 표현하는 경우에 설정한다. 컬럼타입이 "Text", "Int", "Float", "AutoSum", "AutoAvg" 인 경우에 사용할 수 있다. 여기에서 설정하는 이미지는 컬럼에 대한 기본 이미지 이며 조회 데이터 구조에서 셀 별로 설정이 가능하다.
>
> **ImgAlign**는 Image 속성을 사용한 경우 이미지의 위치를 설정한다. "Left"로 설정하는 경우 텍스트의 왼쪽에 이미지가 표시되고 "Right"로 설정하는 경우 텍스트의 오른쪽에 이미지가 표시된다. 설정을 하지 않는 경우 기본값은 "Left"이다.
>
> **ImgHeight**는 Type이 "Image" 이거나 "Image" 속성을 사용하는 경우 표시되는 이미지의 높이 값을 설정한다. 기본적으로 0값이 설정되며 0으로 설정하는 경우 표시되는 이미지는 원본 사이즈로 표시된다
>
> **ImgWidth**는 Type이 "Image" 이거나 "Image" 속성을 사용하는 경우 표시되는 이미지의 너비 값을 설정한다. 기본적으로 0값이 설정되며 0으로 설정하는 경우 표시되는 이미지는 원본 사이즈로 표시된다.
>
> **InsertEdit**는 트랜잭션 상태가 입력인 데이터에 해서 Edit 가능 여부를 설정하며, 기본적으로 1값이 설정된다.
>
> **ItemCode**는 한 셀안에 2개이상의 체크박스(멀티 체크) 구성시 해당 아이템별 코드를 구분자 "\|"로 연결한 문자열로 설정한다. 해당 속성은 컬럼타입이 "CheckBox", "DummyCheck"에서만 사용이 가능 하다.
>
> **ItemText**는 한 셀안에 2개이상의 체크박스(멀티 체크) 구성시 해당 아이템별 텍스트(라벨)을 구분자 "\|"로 연결한 문자열로 설정한다. 해당 속성은 컬럼타입이 "CheckBox", "DummyCheck"에서만 사용이 가능 하다.
>
> **KeyField**는 데이터의 필수입력 항목 여부를 설정하는 것으로 1인 경우 저장 함수 호출 시 셀에 데이터가 없는 경우 경고 메시지를 표시하고, Edit 하도록 유도한다. 기본적으로 0값이 설정된다.
>
> **LevelSaveName**은 트리시트에서 데이터를 저장할 때 트리레밸을 넘겨주기 위해서 설정하는 변수이다. 변수명을 설정하지 않을 경우 해당 행의 트리레벨은 서버로 전달되지 않는다.
>
> **MaxCheck**는 멀티 체크를 구성시 최대 허용 체크 개수를 설정한다. 설정값이 0인 경우는 최대 허용에 대한 제한을 두지 않는다. 해당 속성은 "CheckBox", "DummyCheck" 컬럼타입에 ItemText 속성이 설정된 경우에만 유효 하다.
>
> **MaximumValue**는 Format이 숫자와 관련된 포맷인 Integer, Float, NullInteger, NullFloat 일 때, 편집 시 입력할 수 있는 최대값을 설정한다.
>
> **MenuFilter** Filter 설정시 사용자가 원하는 옵션 값을 선택할 수 있다. 단 지원 가능한 타입내에서 설정 가능하다. (여러개 선택시 '\|' 구분자로 연결)

| 설정값 | 설명                 |       타입       |
|:------:|----------------------|:----------------:|
|   0    | 사용안함             | Text Number Date |
|   1    | 같음                 | Text Number Date |
|   2    | 같지 않음            | Text Number Date |
|   3    | 작음                 |   Number Date    |
|   4    | 같거나 작음          |   Number Date    |
|   5    | 큼                   |   Number Date    |
|   6    | 같거나 큼            |   Number Date    |
|   7    | 단어로 시작함        |    Text Date     |
|   8    | 단어로 시작하지 않음 |    Text Date     |
|   9    | 단어로 끝남          |    Text Date     |
|   10   | 단어로 끝나지 않음   |    Text Date     |
|   11   | 포함함               |    Text Date     |
|   12   | 포함하지 않음        |    Text Date     |

> **MinimumValue**는 Format이 숫자와 관련된 포맷인 Integer, Float, NullInteger, NullFloat 일 때, 편집 시 입력할 수 있는 최소값을 설정한다.
>
> **MultiLineText**는 데이터타입이 "Text"인 경우 다중라인 입력여부를 설정한다. 기본적으로 0값이 설정된다.
>
> **NumberSort**는 데이터타입이 "Text", "Popup" 인 경우 Sort 시 문자형 정렬방식으로 처리하게 되는데, 이를 숫자형 정렬방식으로 사용하고자 하는 경우에 이 속성을 사용한다. 설정하지 않은 경우 기본값은 0으로 문자형 정렬방식으로 처리 된다.
>
> **PointCount**는 컬럼타입이 Float 인 경우 소수점 이하의 자리 수를 설정한다.
>
> 설정하지 않은 경우 Format 설정 값을 따르며 설정한 경우 Format 설정 값은 무시되고 재설정 된다.
>
> **PhoneMask** 속성은 컬럼 타입이 PhoneNo인 경우 전화번호 포맷의 원하는 위치에 마스킹 처리할 수 있는 속성이다. 해당 속성은 “PhoneMask”:[“#”, “\*”, “#”] 과 같이 배열안에 마스킹 할 위치를 \* 로 설정하여 사용한다.
>
> **PopupButton** 속성은 대상 셀에 팝업 버튼 사용여부에 대한 컬럼단위로 설정할 수 있는 속성이다. "Text", "Int", "Float", "AutoSum", "AutoAvg" 컬럼타입에서 설정 할 수 있으며, 별도 설정이 없는 경우 기본값인 0(false)로 처리 된다.
>
> **PopupCheckEdit**는 컬럼팝업을 설정 했을 경우 선택한 행의 데이터 편집가능 여부를 확인하여 편집 가능한 데이터만 변경하는 경우는 1로 설정한다. 기본적으로 0값이 설정된다.
>
> **PopupCode**는 PopupText에 매핑되는 코드값을 "\|"로 연결하여 구성하며 PopupText 항목의 개수와 동일하여야 한다. 이 속성을 설정하는 경우에는 팝업 메뉴에서 항목을 선택 시 해당 컬럼의 옆 컬럼에 매핑되는 코드 값이 설정된다.
>
> **PopupText**는 마우스 오른쪽 버튼 클릭시 보여지는 팝업 메뉴 목록을 설정할 항목을 "\|"로 연결하여 구성한다.
>
> **RadioIcon**은 CheckBox, DummyCheck, DelCheck, Radio 컬럼타입에 대하여 데이터 셀에 표현되는 이미지 모양을 설정한다. 1로 설정하는 경우에는 라디오 버튼 모양으로 표시되고 0으로 설정하는 경우에는 체크박스 모양으로 표시된다. 기본값은 Radio 컬럼타입은 1 그외의 컬럼타입은 0이다.
>
> **RowMerge**는 데이터 컬럼에 대한 가로 머지 허용 여부를 설정한다. 기본적으로 1값이 설정된다.
>
> **RowSpan**은 단위 데이터 행 구조에서 단위 데이터 행 범위 내에서 고정으로 적용 할 RowSpan 범위를 설정 한다. 이 속성 설정시 데이터의 동일 유무와 관계없이 셀 병합 처리를 하여 표현 된다. 이 속성은 단위 데이터 행 구조에서 만 유효하며, 해당 속성을 사용하기 위해서는 MergeSheet 설정값을 3 또는 8로 설정 하여야 한다. (연관 속성 : ColSpan)
>
> **Save** 속성은 저장 또는 저장 관련 메소드에서 해당 컬럼의 값을 포함하여 서버로 전달 또는 추출할지 여부를 설정 한다. 일반적으로 **SaveName** 속성을 정의 해야하고, 저장시 서버로 전달이 필요 없는 경우 이 속성값을 0(false)로 설정 한다. (**SaveName** 속성을 설정하지 않으면 기본적으로 전달하지 않는다.)
>
> 이 속성은 **SaveName** 속성이 설정되어 있는 경우에만 유효하게 동작 한다.
>
> **SaveName**은 데이터를 저장할 때 사용하는 변수 명을 설정한다. 변수 명을 설정하지 않을 경우 기본적으로 컬럼 순서대로 C1, C2, … 로 설정된다. 변수명의 조합은 문자(영문, 한글) 또는 문자+숫자 형태로 사용가능하며 숫자로만 된 형태는 지원하지 않는다.
>
> **ShowCol** 속성은 ComboText에서 다중컬럼 형태의 콤보를 사용할때 콤보 선택시 보여지는 기준 컬럼을 설정 한다. 설정하지 않은 경우 ComboText에 처음 문자열이 보여진다.
>
> **Sort**는 헤더 셀을 클릭 시 소트 처리 가능 여부를 설정한다. 기본적으로 1값이 설정된다.
>
> **StaticPassword**는 Pass 타입에서 ibmsg의 SYS_PDWord 값으로 고정표현할지 데이터 길이에 따라 ‘\*’를 표현할지 여부를 선택한다. 기본속성은 1이며 고정된 값을 표현한다.
>
> **SumType**은 AutoSum 컬럼에 대한 합계 계산 방식을 설정한다. 설정값에 따라 합계, 평균, 건수, 최대값, 최소값을 계산하여 합계행에 표시 한다. 컬럼 중 AutoSum 컬럼이 1개 이상인 경우에 합계행은 설정에 따라 상단 또는 하단에 표시된다. 컬럼에 AutoSum 속성이 true일 경우 타입과 무관하게 합계 계산을 할 수 있다. 해당 속성의 설정값은 대소구분없이 설정이 가능하며 설정에 따른 계산방식은 다음과 같다.

| 설정값  | 설명                     |
|:-------:|--------------------------|
|  "Sum"  | 합계 계산 처리 (Default) |
|  "Avg"  | 평균 계산 처리           |
| "Count" | 건수 계산 처리           |
|  "Max"  | 최대값 계산 처리         |
|  "Min"  | 최소값 계산 처리         |

> **ToolTip**은 데이터 영역에 풍선도움말 사용 여부를 설정한다. Boolean 으로 설정한 경우 사용함/사용안함으로 설정되고, 설정인 경우 셀의 데이터와 동일한 내용의 풍선도움말을 표시 한다. 문자열로 설정한 경우 해당 문자열로 풍선도움말을 표시 한다.
>
> **ToolTipText**는 헤더 행의 풍선도움말에 표시할 문자열을 설정한다. 기본적으로 빈 값이 설정된다.
>
> **Transaction**은 Status 컬럼이 있는 경우 해당 셀의 값 변경시 트랜잭션 관리 허용여부를 설정 한다. 해당 속성의 설정을 0으로 설정시 해당 셀의 값을 변경하더라고 Status 컬럼의 트랜잭션 상태가 변경되지 않는다.
>
> **TreeCheck**는 트리 기준컬럼에 체크박스 사용여부에 대한 설정이다. TreeCol이 설정되어있는 컬럼에서만 해당 속성이 유효하고, 1(true)로 설정시 트리기준 컬럼의 셀별 좌측에 체크박스가 표시 된다.
>
> **TreeCol**은 트리형태 조회의 경우 기준컬럼 여부를 설정한다.
>
> **TrueValue, FalseValue**는 CheckBox 형태인 컬럼에서 기존에 지원하던 0,1 이외의 지정한 값을 사용할 수 있도록 사용자가 지정할 수 있게 하는 기능이다. 예를 들어 TrueValue:"T", FalseValue:"F"로 지정하게 되면 1 대신 "T", 0 대신 "F" 를 사용하여 값을 나타낼 수 있다.
>
> **UpdateEdit**는 트랜잭션 상태가 조회인 데이터에 대해 Edit 가능 여부를 설정하며, 기본적으로 1값이 설정된다.
>
> **Width**는 컬럼에 대한 픽셀 단위 너비 설정으로 설정하지 않을 경우 헤더 Text의 너비에 맞게 자동 설정된다.
>
> **Wrap**는 컬럼너비에 따라 자동 줄 바꿈 여부를 설정한다. 기본적으로 0값이 설정된다.
>
> **VAlign**는 컬럼 세로 정렬 기능을 설정한다. "Top"으로 설정할 경우 텍스트 및 이미지 등을 최상단으로 정렬하고, "Bottom"으로 설정할 경우 최하단으로 정렬한다. 설정을 하지 않는 경우 기본값은 "Middle"로 중앙으로 정렬된다.
>
> **ZeroToReplaceChar**는 데이터 타입이 "Int", "Float", "AutoSum"이고, 해당 셀의 값이 0일 때, 화면에 0값을 대체하여 표시할 문자 또는 문자열을 설정하는 기능이다. 화면 표시에만 해당 설정한 문자열로 보여지게 되고, 내부에서 처리되는 값는 0으로 처리되기 때문에 저장 또는 문서 연동시에는 해당 설정값으로 처리되지 않는다.

- **Example**

```javascript
//각 컬럼의 기능을 설정한다.
var cols = [
{Type:"Status",Width:60,SaveName:"sStatus",Align:"Center"},
{Type:"DelCheck",Width:60,SaveName:"sDelete",Align:"Center"},
{Type:"Text",Width:100,SaveName:"JOB",Align:"Center"},
{Type:"Combo",Width:100,SaveName:"DEPTNO",Align:"Center"
,ComboText:comboDataArr[0],ComboCode:comboDataArr[1]},
{Type:"Text",Width:60,SaveName:"EMPNO",Align:"Center"},
{Type:"Text",Width:150,SaveName:"ENAME",Align:""},
{Type:"Date",Width:120,SaveName:"HIREDATE",Format:"Ymd"
,Align:"Center",EditLen:8},
{Type:"Text",Width:120,SaveName:"MGR",Align:"Center"},
{Type:"Int",Width:120,SaveName:"SAL",Align:"Right",Format:"NullInteger"},
{Type:"Int",Width:60,SaveName:"COMM",Align:"Right",Format:"Integer"}
];
mySheet.InitColumns(cols);
```

- **제공 버전**

| **7.0.0.0**    |                                                                              |
| -------------- | ---------------------------------------------------------------------------- |
| **7.0.1.0**    | 1. ComboFilter 속성에 대한 앞문자열 일치 형태의 필터링 모드 추가 2. ComboEdit 컬럼 Validation 설정 추가 |
| **7.0.4.4**    | 다중라인 입력모드에 대한 EnterMode 속성 추가                                                |
| **7.0.7.2**    | 팝업버튼 사용여부 설정을 위한 PopupButton 속성 추가                                           |
| **7.0.9.0**    | TreeCheck, CheckSaveName 속성 추가                                               |
| **7.0.10.0**   | GroupSumType 속성 추가                                                           |
| **7.0.11.0**   | 스파크라인 컬럼타입 추가, Chart 속성 추가                                                   |
| **7.0.12.0**   | SumType 속성 추가, ExcludeEmpty 속성 적용범위 확장(건수) AutoAvg 컬럼타입 삭제                   |
| **7.0.12.2**   | RowMerge, FitColWidth 속성 추가                                                  |
| **7.0.12.3**   | ItemCode, ItemText, MaxCheck 속성 추가                                           |
| **7.0.13.3**   | Transaction 속성 추가                                                            |
| **7.0.13.5**   | "Text", "Popup" 컬럼타입에서의 다중 포맷 설정 지원 "PostNo" 포맷에 대한 기존 6자리, 신규 5자리 포맷지원      |
| **7.0.13.9**   | "Button" 컬럼타입 추가, ClassName 속성 추가                                            |
| **7.0.13.13**  | EditPointCount 속성 추가                                                         |
| **7.0.13.16**  | ActionMenu 속성 추가                                                             |
| **7.0.13.24**  | EmptyToReplaceChar, ZeroToReplaceChar 속성 추가                                  |
| **7.0.13.29**  | Save 속성 추가 CalcLogic 속성 개선 (Object 타입 설정 기능 추가)                              |
| **7.0.13.34**  | NumberSort 속성 추가                                                             |
| **7.0.13.50**  | ColMerge 속성 개선 (가상 셀병합 모드 추가, 타입변경)                                          |
| **7.0.13.53**  | StaticPassword 속성 추가                                                         |
| **7.0.13.107** | Acceptkeys 속성에 한글 옵션 추가                                                      |
| **7.0.13.123** | GroupSumType 속성에 평균 옵션 추가, AutoSum 속성 추가                                     |
| **7.0.13.125** | ComboDisabled 속성 추가.                                                         |
| **7.0.13.141** | CopyPaste 속성 추가.                                                             |