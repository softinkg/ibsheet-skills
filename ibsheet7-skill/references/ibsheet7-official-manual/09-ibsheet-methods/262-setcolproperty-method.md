# SetColProperty Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SetColProperty Method

---

- **기능**

> InitColums Method를 통해 정의후 특정 컬럼의 속성 정의를 동적으로 변경하여 사용 하고자 하는 경우에 이 메소드를 사용한다. 동적으로 변경된 속성은 데이터 재조회시 적용되므로 데이터 조회 이전에 변경하여야 한다.
>
> 이 메소드를 통해 재설정이 가능한 속성은 다음과 같다.

| 속성                 | 타입              | 설명                                                                                                                                                                                                                                                                                                     |
| ------------------ | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| AcceptKeys         | String          | 입력허용키 설정 "N" : 숫자만 허용 "E" : 영문만 허용 "K" : 한글만 허용 "N\|E" : 숫자, 영문만 허용 "N\|E\|[사용자정의문자]" : 숫자, 영문과 사용자정의문자로 설정한 문자 허용 예) "N\|[abc!]" 설정 시 숫자와 a, b, c, ! 문자만 입력 가능 사용자 정의 문자열은 꼭 대괄호로 묶어서 설정해야 하며 사용자정의문자와 숫자,영문 설정문자의 합집합으로 처리된다. AcceptKeys 와 ExceptKeys를 둘다 설정하고 설정키 내에 동일 문자가 있는 경우 해당 문자는 입력불가 처리된다. |
| ActionMenu         | Object[]        | 컨텍스트 메뉴                                                                                                                                                                                                                                                                                                |
| Align              | String          | 데이터의 정렬                                                                                                                                                                                                                                                                                                |
| AllowNull          | Boolean         | 숫자계열 컬럼에 빈값 허용 여부 설정                                                                                                                                                                                                                                                                                   |
| ApproximateType    | Number          | 근사값처리방식 (1:반올림, 2:내림, 3:올림)                                                                                                                                                                                                                                                                            |
| ButtonUrl          | String/Number   | 팝업 버튼의 이미지 경로 또는 이미지리스트의 Index                                                                                                                                                                                                                                                                         |
| CalcLogic          | String / Object | 컬럼별 계산식 문자열 또는 설정 객체 세부설명은 InitColumns 메소드 참고                                                                                                                                                                                                                                                          |
| Chart              | Object          | 스파크라인 차트 타입에 대한 세부 속성 설정 세부설명은 InitColumns 메소드 참고                                                                                                                                                                                                                                                      |
| ColMerge           | Number          | 컬럼의 셀 병합 처리 방법 세부설명은 InitColumns 메소드 참고                                                                                                                                                                                                                                                                |
| ComboCode          | String          | 콤보 리스트의 코드 집합                                                                                                                                                                                                                                                                                          |
| ComboDisabled      | String          | 콤보 리스트의 선택 불가능한 item 설정.                                                                                                                                                                                                                                                                               |
| ComboText          | String          | 콤보 리스트의 문자열 집합                                                                                                                                                                                                                                                                                         |
| CustomDate         | Number          | 사용자 정의 날짜 사용여부                                                                                                                                                                                                                                                                                         |
| DefaultValue       | String          | 신규입력시 기본값 설정                                                                                                                                                                                                                                                                                           |
| Edit               | Boolean         | 편집가능 여부                                                                                                                                                                                                                                                                                                |
| EditLen            | Number          | 데이터의 입력가능한 글자수                                                                                                                                                                                                                                                                                         |
| EmptyToReplaceChar | String          | 빈값인 경우 대체하여 보여줄 문자 설정                                                                                                                                                                                                                                                                                  |
| EnterMode          | Boolean         | 다중라인 입력모드(MultiLineText)에서 Enter 키 입력에 대한 개행 처리 여부 (Default=0)                                                                                                                                                                                                                                         |
| ExceptKeys         | String          | 입력제외키 설정 "N" : 숫자 입력 불가 "E" : 영문 입력 불가 "N\|E" : 숫자, 영문 입력 불가 "N\|E\|[사용자정의문자]" : 숫자, 영문과 사용자정의문자로 설정한 문자 입력 불가 예) "N\|[abc!]" 설정 시 숫자와 a, b, c, ! 문자만 입력 불가 사용자 정의 문자열은 꼭 대괄호로 묶어서 설정해야 하며 사용자정의문자와 숫자,영문 설정문자의 합집합으로 처리된다. AcceptKeys 와 ExceptKeys를 둘다 설정하고 설정키 내에 동일 문자가 있는 경우 해당 문자는 입력불가 처리된다.     |
| FalseValue         | String          | 0 이외의 CheckBox 형태 컬럼의 False값 지정. "F" 으로 지정한 경우 0 대신 "F"을 True 값으로 사용 가능.                                                                                                                                                                                                                               |
| FitColWidth        | Boolean         | FitColWidth 메소드 호출시 비율에 의한 너비 재조정 허용 여부                                                                                                                                                                                                                                                                |
| Focus              | Boolean         | 포커스 허용 여부                                                                                                                                                                                                                                                                                              |
| Format             | String          | 데이터의 Mask 적용 형태                                                                                                                                                                                                                                                                                        |
| FormatFix          | Boolean         | GetCellValue 시 GetCellText 값을 반환 할지 여부. 특히 True 로 설정시 저장할 때 Format 이 설정된 상태로 저장한다.                                                                                                                                                                                                                     |
| HoverUnderline     | Boolean         | 마우스오버시 언더라인 여부                                                                                                                                                                                                                                                                                         |
| Image              | String          | 이미지 표현시 Url                                                                                                                                                                                                                                                                                            |
| ImgHeight          | Number          | 이미지 높이                                                                                                                                                                                                                                                                                                 |
| ImgWidth           | Number          | 이미지 너비                                                                                                                                                                                                                                                                                                 |
| InputCaseSensitive | Number          | 입력시 영문에 대한 대소구문 자동 치환 처리에 대한 설정 0 : 별도 처리 하지 않음 (기본값) 1 : 대문자로 치환 2 : 소문자로 치환                                                                                                                                                                                                                          |
| ItemCode           | String          | 멀티체크 아이템의 코드를 구분자 "\|"로 연결한 문자열                                                                                                                                                                                                                                                                        |
| ItemText           | String          | 멀티체크 아이템의 텍스트를 구분자 "\|"로 연결한 문자열                                                                                                                                                                                                                                                                       |
| KeyField           | Boolean         | 필수 입력 항목                                                                                                                                                                                                                                                                                               |
| MinWidth           | Number          | 컬럼 최소 가로크기                                                                                                                                                                                                                                                                                             |
| MaxCheck           | Number          | 멀티체크의 최대 선택 개수 설정                                                                                                                                                                                                                                                                                      |
| MultiLineText      | Boolean         | 다중라인 입력여부                                                                                                                                                                                                                                                                                              |
| NumberSort         | Boolean         | 숫자형 Sort 처리 사용 여부                                                                                                                                                                                                                                                                                      |
| PointCount         | Number          | 컬럼포맷이 Float 인 경우 소수점 이하의 자리수                                                                                                                                                                                                                                                                           |
| PopupCode          | String          | 팝업메뉴의 코드 집합                                                                                                                                                                                                                                                                                            |
| PopupText          | String          | 팝업메뉴의 문자열 집합                                                                                                                                                                                                                                                                                           |
| RadioIcon          | Boolean         | 데이터 셀내의 체크박스 계열의 이미지 모양 설정                                                                                                                                                                                                                                                                             |
| ShowCol            | Number          | 멀티콤보 설정 시 컬럼 값으로 출력할 컬럼 설정                                                                                                                                                                                                                                                                             |
| ToolTip            | Boolean/String  | 셀의 풍선도움말 표시 여부 또는 설정할 문자열                                                                                                                                                                                                                                                                              |
| Transaction        | Boolean         | 트랜잭션 허용 여부 (Default=1)                                                                                                                                                                                                                                                                                 |
| TreeCol            | Boolean         | 트리 기준컬럼 설정여부                                                                                                                                                                                                                                                                                           |
| TrueValue          | String          | 1 이외의 CheckBox 형태 컬럼의 True 값 지정. "M" 으로 지정한 경우 1 대신 "M"을 True 값으로 사용 가능.                                                                                                                                                                                                                               |
| Width              | Number          | 컬럼의 너비                                                                                                                                                                                                                                                                                                 |
| ZeroToReplaceChar  | String          | 값이 0인 경우 대체하여 보여줄 문자 설정                                                                                                                                                                                                                                                                                |
| StaticPassword     | Boolean         | 값이 0인 경우 데이터 길이만큼 ‘*’ 의 수를 표현한다.                                                                                                                                                                                                                                                                       |

> 각 속성의 상세 설명은 InitColumns Method 설명을 참조 한다.

- **Syntax**

|        |                                               |
|:------:|-----------------------------------------------|
| Syntax | ObjId.**SetColProperty**(DataRow, Col, Prop); |

- **Info**

> **Return**: None

| Parameter | Type            | 필수여부 | 설 명                      |
| --------- | --------------- | ---- | ------------------------ |
| DataRow   | Number          | 필수   | 단위데이터행 Index             |
| Col       | Number / String | 필수   | 대상 컬럼의 Index 또는 SaveName |
| Prop      | Object          | 필수   | 컬럼의 속성 정의 객체             |

- **Example**

```javascript
// 3번째 컬럼의 콤보 목록을 변경
var info = {ComboText: "신규|진행중|완료 ", ComboCode: " 01|02|03" };
mySheet.SetColProperty(0, 3, info);
// 단위데이터행 1번째, 3번째 컬럼의 콤보 목록을 변경
var info = {ComboText: "신규|진행중|완료 ", ComboCode: " 01|02|03" };
mySheet.SetColProperty(1, 3, info);
// 4번째 컬럼에 허용키, 제외키 설정
var info = {AcceptKeys:"N|E|[!$%]",ExceptKeys:"[123ab]"};
mySheet.SetColProperty(0, 4 ,info);
```

- **제공 버전**

|  **7.0.0.0**   |                                                     |
|:--------------:|-----------------------------------------------------|
|  **7.0.4.4**   | 다중라인 입력모드에 대한 EnterMode 속성 추가        |
|  **7.0.7.2**   | 팝업버튼 사용여부 설정을 위한 PopupButton 속성 추가 |
|  **7.0.11.0**  | Chart 속성 추가                                     |
|  **7.0.12.2**  | FitColWidth 속성 추가                               |
|  **7.0.12.3**  | ItemCode, ItemText, MaxCheck 속성 추가              |
|  **7.0.13.3**  | Transaction 속성 추가                               |
| **7.0.13.16**  | ActionMenu 속성 추가                                |
| **7.0.13.22**  | CalcLogic 속성 추가                                 |
| **7.0.13.24**  | EmptyToReplaceChar, ZeroToReplaceChar 속성 추가     |
| **7.0.13.29**  | CalcLogic 속성 개선 (Object 타입 설정 기능 추가)    |
| **7.0.13.34**  | NumberSort 속성 추가                                |
| **7.0.13.53**  | StaticPassword 속성 추가                            |
| **7.0.13.125** | ComboDisabled 속성 추가.                            |
| **7.0.13.223** | ColMerge 속성 추가                                  |