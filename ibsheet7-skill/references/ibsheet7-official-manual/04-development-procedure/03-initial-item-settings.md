# 4.3 초기항목설정

> **IBSheet7 개발자 가이드** > 개발 절차 > 4.3 초기항목설정

---

> 개체가 생성된 후 페이지가 onload 될때 시트의 초기 항목을 설정한다. 아래와 같이 Body 태그의 onload 이벤트에서 IBSheet에 대한 초기 항목을 설정할 함수를 정의 한다.

```
<Body onload="기본 속성을 설정할 함수명()">
```

> Body 태그의 onload 이벤트에서 정의하는 것은 페이지의 로드가 완료 되는 시점에 IBSheet의 객체도 생성이 완료되므로 그때 IBSheet의 제공 기능들을 사용할 수 있기 때문이다. 만약 객체 생성 전에 IBSheet 기능을 사용하려고 한다면 자바스크립트 오류가 발생 할 수 있다.
>
> 초기 항목 설정에 필요한 처리 항목은 아래와 같다.

|                    |                    |           |
|:------------------:|:------------------:|:---------:|
|   기본 코드 절차   | IBSheet 제공 함수  | 호출 횟수 |
| 1\. 시트 정보 설정 |  SetConfig Method  |     1     |
| 2\. 헤더 정보 설정 | InitHeaders Method |     1     |
| 3\. 컬럼 정보 설정 | InitColumns Method |     1     |

> 아래의 절차에 따라 페이지 설정해 보도록 한다.### 4.3.1. 시트 기본 설정

|                                 |
|---------------------------------|
| **IBSheet객체.SetConfig(cfg);** |

> 시트 전반적이 기능 설정 (조회방식,머지유형,소팅 개수, 합계행위치 등)한다.
>
> 전달되는 인자의 형식은 JSON 타입으로 설정 하고자 하는 정보를 JSON 형태로 구성하여 전달한다.
>
> 예) var cfg= {FrozenCol:3 , MergeSheet:msPrevColumnMerge + msHeaderOnly };
>
> IBSheet객체.SetConfig(cfg);
>
> 이 함수를 통하여 시트의 기본적인 환경을 설정한다.

| 설정변수            | 타입      | 설명                                                                                                                                                     |
| --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| DataRowMerge    | Boolean | 전체행의 가로머지 허용여부 (Default=0)                                                                                                                             |
| FrozenCol       | Integer | 좌측에 고정 컬럼의 수                                                                                                                                           |
| MergeSheet      | Integer | 머지 종류를 설정 msNone : 머지없음 msHeaderOnly : 헤더만 머지 msPrevColumnMerge : 데이터영역 앞컬럼기준 머지 msAll : 전체 머지 msHeaderOnly+msPrevColumnMerge : 헤더영역 머지 + 데이터영역 앞컬럼 머지 |
| Page            | Integer | 한번에 렌더링할 행의 수. 큰 값을 입력시 대량데이터가 한번에 화면에 표시되면서 성능 저하를 발생시킬 수 있다. 가급적 별도 설정하지 말고 Default를 따를 것.                                                           |
| AutoFitColWidth | String  | 컬럼 너비 자동 조정 시점 설정. "search\|init\|resize"                                                                                                              |
| SearchMode      | Integer | 조회 방식 설정 smGeneral : 전체보기조회 (권장하지 않음) smClientPaging : 페이징 조회 smLazyLoad : 스크롤 조회(권장, 기본값) smServerPaging : 서버 스크롤 페이징 조회 (5000건 이상의 대용량시 권장)          |
| SizeMode        | Integer | 사이즈 방식 설정 0: 사이즈 고정 1: 높이를 스크롤 없이 자동 설정 2: 너비를 스크롤 없이 자동 설정 3: 높이, 너비를 스크롤 없이 자동 설정 4: 설정한 높이 이전까지 스크롤 없이 높이 자동 설정                                     |
| SumPosition     | Boolean | 합계행 위치(1: 하단 고정, 0: 상단 고정)                                                                                                                             |
| SumZeroValue    | String  | 합계 행의 합계값이 0 인경우 치환값 설정                                                                                                                                |
| ToolTip         | Boolean | 셀의 풍선도움말을 표시한다.                                                                                                                                        |

> *※ 세부 정보는 [SetConfig 메소드](#_SetConfig_Method)의 설명 참조*### 4.3.2. 헤더 정보 설정

|                                                 |
|-------------------------------------------------|
| **IBSheet객체.InitHeaders(headers, [info]);** |

> 헤더행의 타이틀과 해더의 기능(소팅,이동,크기조정 등) 사용여부를 설정한다.  
> 예) var headers = [ {Text:"사원정보\|사원정보\|사원정보", Align:" Center"} ,
>
> {Text:"사원명\|사원번호\|입사일", Align:" Center"}];
>
> var info = {Sort:1, ColMove:1, ColResize:0, HeaderCheck:0};
>
> IBSheet객체.InitHeaders(headers , info );

| 설정변수    |             | 타입      | 설명                           |
| ------- | ----------- | ------- | ---------------------------- |
| headers | Text        | String  | 헤더에 표시할 Text를 "\|"로 연결한 문자열  |
| headers | Align       | String  | 헤더 텍스트의 정렬방법                 |
| info    | Sort        | Boolean | 헤더 클릭 시 소트 가능 여부 (Default=1) |
| info    | ColMove     | Boolean | 헤더 컬럼 이동 가능 여부 (Default=1)   |
| info    | ColResize   | Boolean | 컬럼 너비 ReSize 여부 (Default=1)  |
| info    | HeaderCheck | Boolean | 헤더에 전체 체크 표시 여부 (Default=1)  |

> *※ 세부 정보는 [InitHeaders 메소드](#initheaders-method)의 설명 참조*### 4.3.3. 컬럼 정보 설정

|                                   |
|-----------------------------------|
| **IBSheet객체.InitColumns(cols)** |

> 이 함수를 통하여 컬럼에 대한 기본 속성(타입,포멧,너비,정렬 등) 을 설정한다.
>
> 예) var cols = [
>
> {Type:"Text", Width:100 ,SaveName:"sText", Align:"Left"},
>
> {Type:"Int", Width:80 ,SaveName:"sNumber", Format:"NullInteger"}
>
> ];
>
> IBSheet객체.InitColumns(cols);
>
> 컬럼별로 설정 할 수 있는 속성은 다음과 같다.

| 속성              | 타입      | 설명                                                                         |
| --------------- | ------- | -------------------------------------------------------------------------- |
| Type            | String  | 컬럼의 데이터 타입                                                                 |
| Width           | Integer | 컬럼의 너비                                                                     |
| MinWidth        | Integer | 컬럼의 최소 너비                                                                  |
| Align           | String  | 데이터의 정렬                                                                    |
| SaveName        | String  | 데이터 저장 또는 조회시 사용하는 변수명                                                     |
| Edit            | Boolean | 편집가능 여부                                                                    |
| EditLen         | Integer | 데이터의 입력가능한 글자수                                                             |
| Format          | String  | 데이터의 Mask 적용 형태                                                            |
| ComboText       | String  | 콤보 리스트의 문자열 집합                                                             |
| ComboCode       | String  | 콤보 리스트의 코드 집합                                                              |
| MultiLineText   | Boolean | 다중라인 입력여부                                                                  |
| Wrap            | Boolean | 자동 줄바꿈 여부                                                                  |
| TreeCol         | Boolean | 트리 기준컬럼                                                                    |
| KeyField        | Boolean | 필수 입력 항목                                                                   |
| CalcLogic       | String  | 컬럼별 계산식                                                                    |
| ColMerge        | Boolean | 컬럼 머지 허용여부                                                                 |
| Hidden          | Boolean | 컬럼 숨김 여부                                                                   |
| ImgWidth        | Integer | 이미지 너비                                                                     |
| ImgHeight       | Integer | 이미지 높이                                                                     |
| PopupText       | String  | 팝업메뉴의 문자열 집합                                                               |
| PopupCode       | String  | 팝업메뉴의 코드 집합                                                                |
| PopupCheckEdit  | Boolean | 팝업메뉴 설정시 편집가능 여부                                                           |
| UpdateEdit      | Boolean | 트랜잭션이 "조회"인 상태에서 데이터의 Edit 가능 여부                                           |
| InsertEdit      | Boolean | 트랜잭션이 "입력"인 상태에서 데이터의 Edit 가능 여부                                           |
| LevelSaveName   | String  | 트리 데이터 저장시 사용하는 변수명                                                        |
| ButtonUrl       | String  | 버튼이미지파일명(Popup 타입일경우)                                                      |
| TrueValue       | String  | 1 이외의 CheckBox 형태 컬럼의 True 값 지정. "M" 으로 지정한 경우 1 대신 "M"을 True 값으로 사용 가능.   |
| FalseValue      | String  | 1 이외의 CheckBox 형태 컬럼의 False 값 지정. "F" 으로 지정한 경우 0 대신 "F"룰 False 값으로 사용 가능. |
| MaximumValue    | Number  | 숫자포맷일 때 편집시 입력할수 있는 최대값                                                    |
| MinimumValue    | Number  | 숫자포맷일 때 편집시 입력할수 있는 최소값                                                    |
| PointCount      | Integer | 컬럼타입이 Float 인 경우 소수점 이하의 자리수                                               |
| FullInput       | Boolean | 컬럼타입이 단일행 문자열인 경우 전체길이(EditLen)만큼의 입력 여부                                   |
| ToolTipText     | String  | 풍선 도움말에 설정할 문자열                                                            |
| Ellipsis        | Boolean | 말줄임 여부                                                                     |
| BackColor       | String  | 배경 색상                                                                      |
| FontColor       | String  | 폰트 색상                                                                      |
| ApproximateType | Integer | 근사값처리방식 설정 (1:반올림, 2:내림, 3:올림)                                             |
| ShowCol         | Number  | 멀티콤보 설정 시 컬럼 값으로 출력할 컬럼 설정                                                 |

> 각 속성의 세부 설정값
>
> **Type**은 해당 컬럼에 대한 Type 설정으로 다음과 같은 값을 설정 할 수 있다.

|  |  |
|:--:|:--:|
| Type | 설명 |
| Text | 기본 문자열 데이터 |
| Status | 트랜잭션 상태를 표시하고, 담고 있는 데이터 |
| DelCheck | 삭제 처리만 담당하는 CheckBox 형태 데이터 |
| CheckBox | CheckBox 형태 데이터 |
| DummyCheck | CheckBox 형태이나 체크/언체크시 상태를 변화시키지 않음. |
| Radio | 데이터 행 중 하나의 데이터만 체크되는 형태 |
| Combo | Edit 불가능 Combo 데이터 |
| ComboEdit | 자동완성형태의 Combo 데이터 |
| AutoSum | 자동 합계 계산을 위한 데이터 타입으로, 기본포맷은 NullFloat으로, 포맷이 “Integer”, “#,###”, “#,##0” 등의 경우에 한해 소수점 이하를 버림 |
| Image | Edit 불가능한 단순 이미지 표현 형태 데이터 |
| Int | 정수형 데이터 타입으로, 값이 실수인 경우 소수점 이하를 버림 |
| Float | 실수형 타입 |
| Date | 날짜형 타입 |
| Popup | 팝업을 사용한 데이터 |
| Pass | 패스워드 형태 데이터 |
| Seq | DB의 시퀀스처럼 무조건 값이 증가하는 값이며, Edit가 불가능한 형태의 데이터 |
| Html | Html 태그 형태를 표현하는 데이터 타입 |
| Result | 저장 처리 결과를 표시하는 데이터 타입 |
| Sparkline | 스파크라인 차트를 표현하는 데이터 타입 |
| Button | 버튼 형태를 표현하는 데이터타입 |

> **Width**는 컬럼에 대한 픽셀 단위 너비 설정으로, 설정하지 않을 경우 헤더 Text의 너비에 맞게 자동 설정된다.
>
> (참고. 너비설정과 관련하여 설정한 너비보다 줄어들지 않게하는 **MinWidth**도 있다.)
>
> **Align**은 데이터에 대한 정렬 설정 Left, Center, Right 값을 설정한다.

|           |                           |
|:---------:|:-------------------------:|
| DataAlign |           설명            |
|   Left    | 좌측 정렬 데이터(Default) |
|  Center   |    가운데 정렬 데이터     |
|   Right   |     우측 정렬 데이터      |

> **SaveName**은 데이터를 저장할 때 사용하는 변수 명을 설정한다. 변수명을 설정하지 않을 경우 기본적으로 컬럼 순서대로 C1, C2, … 로 설정된다.
>
> **Edit**는 데이터의 편집가능 여부를 설정한다. 기본적으로 1이 설정된다.
>
> **EditLen**은 데이터의 입력 가능한 글자 수를 설정한다.
>
> **Format**은 데이터에 대한 Mask 적용 형태를 설정하는 것으로 다음과 같은 값을 설정한다. 포맷 설정은 기본제공 외에 사용자가 직접 정의 해서 설정 할 수 있으며 ((ex) Format="#,###.00" or "######-\*\*\*\*\*\*\*" or "MM.dd.yyyy") Type 값에 따라 설정한 Format이 적용 된다.

|  |  |  |
|:--:|:--:|:--:|
| Format | 설명 | 사용가능타입 |
| Ymd | "년월일" 형태. ibmsg의 SYS_d 포맷을 따른다 | Date,Text,Popup |
| Ym | "년월" 형태, ibmsg의 SYS_m 포맷을 따른다. | Date,Text,Popup |
| Md | "월일" 형태. ibmsg의 SYS_M 포맷을 따른다. | Date,Text,Popup |
| Hms | "시분초" 형태. ibmsg의 SYS_T 포맷을 따른다. | Date,Text,Popup |
| Hm | "시분" 형태. ibmsg의 SYS_t 포맷을 따른다. | Date,Text,Popup |
| YmdHms | "년월일시분초" 형태. Ibmsg의 SYS_G 포맷을 따른다 | Date,Text,Popup |
| YmdHm | "년월일시분" 형태. Ibmsg의 SYS_g 포맷을 따른다 | Date,Text,Popup |
| Integer | 정수 형태, 기본 값 0 | Int,AutoSum,AutoAvg |
| NullInteger | 정수 형태, 기본 값 null | Int,AutoSum,AutoAvg |
| Float | 실수 형태, 기본 값 0 | Float,AutoSum,AutoAvg |
| NullFloat | 실수 형태, 기본 값 null | Float,AutoSum,AutoAvg |
| IdNo | 주민등록번호 형태 | Text |
| SaupNo | 사업자번호 형태 | Text |
| PostNo | 우편번호 형태 | Text |
| CardNo | 카드번호 형태 | Text |
| PhoneNo | 전화번호 형태 | Text |
| Number | 숫자 형태(특정 포맷없이 숫자키만 입력받는 형태) | Text |

> **ComboText**는 Type이 "Combo" 또는 "ComboEdit"인 경우 화면에 보여질 문자열 항목을 "\|"로 연결하여 구성한다.
>
> 콤보리스트를 다중 컬럼 형태로 출력하려면 문자열을 "\t"로 연결하여 구성한다.
>
> 예) ,ComboText:"부서장\t김태신\|과장\t이용구\|대리\t신우용\|대리\t김희석\|사원\t임윤수\|사원\t박수평"  
> 
>
> **ComboCode**는 Type이 "Combo" 또는 "ComboEdit"인 경우 저장될 코드 항목을 "\|"로 연결하여 구성하며 위의 ComboText 항목의 개수와 동일 하여야 한다.
>
> ex ) ComboCode:"01\|02\|03\|A7\|B5"
>
> **ShowCol** 속성은 ComboText에서 다중컬럼 형태의 콤보를 사용할때 콤보 선택시 보여지는 기준 컬럼을 설정 한다. 설정하지 않은 경우 ComboText에 처음 문자열이 보여진다.
>
> **MultiLineText**는 Type이 "Text"인 경우 다중라인 입력여부를 설정한다. 기본적으로 0값이 설정된다.
>
> **Wrap**는 컬럼너비에 따라 자동 줄바꿈 여부를 설정한다. 기본적으로 0값이 설정된다.
>
> **TreeCol**은 트리형태 조회의 경우 기준컬럼 여부를 설정한다.
>
> **KeyField**는 데이터의 필수입력 항목 여부를 설정하는 것으로 1인 경우 저장 함수 호출 시 셀에 데이터가 없는 경우 경고 메시지를 표시하고, Edit 하도록 유도한다. 기본적으로 0값이 설정된다.
>
> **CalcLogic**은 해당 데이터에 대한 계산 공식을 설정한다**.** 컬럼 데이터의 값이 공식에 사용 되는 경우 "\|"로 감사서 공식에 설정한다. 기본적으로 공식없은 ""으로 설정된다.
>
> 예를 들어, 5컬럼 값에 2를 곱해서 3컬럼 값을 더해야 한다면 공식은 "\|5\| \* 2 + \|3\|"와 같이 설정된다. 공식이 설정 된 경우 다른 컬럼의 값이 바뀌었거나 조회했을 때 자동으로 계산 처리한다.
>
> 컬럼번호가 아니라 다른컬럼의 SaveName 을 사용하여 공식을 작성할 수도 있다. 예를 들어 위 공식에서 5컬럼의 SaveName이 "pay"였다고 하면 공식은 "\|pay\|\*2+\|3\|"이라고 설정해도 같은 효과를 볼 수 있다.
>
> **ColMerge**는 데이터 컬럼에 대한 세로 머지 가능 여부를 설정한다. 기본적으로 1값이 설정된다.
>
> **Hidden**는 데이터 컬럼 숨김 여부를 설정한다.
>
> **ImgWidth**는 Type이 "Image" 인 경우 표시되는 이미지의 너비값을 설정한다. 기본적으로 0값이 설정되며 0으로 설정하는 경우 표시되는 이미지는 원본 사이즈로 표시된다.
>
> **ImgHeight**는 Type이 "Image" 인 경우 표시되는 이미지의 높이값을 설정한다. 기본적으로 0값이 설정되며 0으로 설정하는 경우 표시되는 이미지는 원본 사이즈로 표시된다  
> (Image 타입을 사용하는 경우, 컬럼의 이미지 사이즈가 동일하다면 ImgWidth,ImgHeight 속성을 설정하는 것으로 조회 속도를 향상시킬 수 있다)
>
> **PopupCode**는 PopupText에 매핑되는 코드값을 "\|"로 연결하여 구성하며 PopupText 항목의 개수와 동일하여야 한다. 이 속성을 설정하는 경우에는 팝업 메뉴에서 항목을 선택 시 해당 컬럼의 옆 컬럼에 매핑되는 코드 값이 설정된다.
>
> **PopupText**는 마우스 오른쪽 버튼 클릭시 보여지는 팝업 메뉴 목록을 설정할 항목을 "\|"로 연결하여 구성한다.
>
> **UpdateEdit**는 트랜잭션 상태가 조회인 데이터에 대해 Edit 가능 여부를 설정하며, 기본적으로 1값이 설정된다.
>
> **InsertEdit**는 트랜잭션 상태가 입력인 데이터에 해서 Edit 가능 여부를 설정하며, 기본적으로 1값이 설정된다.
>
> **LevelSaveName**은 트리시트에서 데이터를 저장할 때 트리레벨을 넘겨주기
>
> 위해서 설정하는 변수이다. 변수명을 설정하지 않을 경우 해당 행의 트리 레벨은
>
> 서버로 전달되지 않는다.
>
> **ButtonUrl**는 컬럼타입이 Popup 일때 Format이 날짜포맷일 경우 해당 버튼이미지를 변경하는 속성이다. 기본적으로 날짜버튼이미지로 설정된다.
>
> (변경할 이미지는 테마폴더 안에 넣는다. 이미지 사이즈는 12\*12)
>
> **TrueValue, FalseValue**는 CheckBox 형태인 컬럼에서 기존에 지원하던 0,1 이외의 지정한 값을 사용할 수 있도록 사용자가 지정할 수 있게 하는 기능이다. 예를 들어 TrueValue:"T", FalseValue:"F" 로 지정하게 되면 1 대신 "T", 0 대신 "F" 를 사용하여 값을 나타낼 수 있다.
>
> **MaximumValue**는 Format이 숫자와 관련된 포멧인 Integer, Float, NullInteger, NullFloat 일때, 편집시 입력할 수 있는 최대값을 설정한다.
>
> **MinimumValue**는 Format이 숫자와 관련된 포멧인 Integer, Float, NullInteger, NullFloat 일때, 편집시 입력할 수 있는 최소값을 설정한다.
>
> **PointCount**는 컬럼타입이 Float 인 경우 소수점 이하의 자리수를 설정한다.
>
> 설정하지 않은 경우 Format 설정값을 따르며 설정한 경우 Format 설정값은 무시되고 재설정 된다.
>
> **FullInput**은 컬럼타입이 단일행 문자열인 경우 EditLen 만큼 모두 입력해야 하는 경우 설정한다. 기본적으로 0값이 설정된다.

**ToolTipText**는 풍선도움말에 표시할 문자열을 설정한다.

> **Ellipsis**는 컬럼 텍스트의 표시글자가 잘릴경우 말줄임 여부를 설정한다. 기본적으로 0값이 설정된다
>
> **BackColor**는 컬럼의 배경색상을 설정한다.
>
> **FontColor**는 컬럼의 폰트색상을 설정한다.
>
> *※ 세부 정보는 [InitColumns 메소드](#initcolumns-method)의 설명 참조*
>
> **  **### 4.3.4. 시트초기화 단순화

> 시트 초기화시 헤더에 타이틀과 각 컬럼의 속성이 각각 InitHeader와 InitColumns메서드를 통해 설정되어 컬럼이 많아지는 경우 타이틀에 해당하는 컬럼을 찾기가 어려운 점이 있다. 따라서 이러한 부분을 하나의 함수를 통해 초기화 하는 방법도 제공한다. Header의 경우 “\|” 구분자 뿐만 아니라, String 배열 형태로도 구현 가능하다. 또한 HeaderHtml 속성을 이용하여 Html 타입의 헤더를 구현 할 수 있다.

```javascript
//배열 선언
var initdata = {};
//SetConfig
initdata.Cfg = {SearchMode:smLazyLoad,Page:50,MergeSheet:msHeaderOnly};
//InitHeaders의 두번째 인자
initdata.HeaderMode = {Sort:1,ColMove:1,ColResize:1,HeaderCheck:0};
//InitColumns + Header Title
initdata.Cols = [
{Header:"결재여부|결재여부",Type:"CheckBox",Width:80,SaveName:"A",ColMerge:0},
{Header:"신청인|신청인",Type:"Text",Width:80,ColMerge:1},
{Header:"신청일자|신청일자",Type:"Date",Width:100,Format:"Ymd"},
{Header:"신청금액|신청금액",Type:"AutoSum",Width:85,SaveName:"B",Format:"Integer"},
{Header:"기간|시작일",Type:"Date",Width:100,SaveName:"C",Format:"Ymd",ColMerge:0},
{Header:"기간|종료일",Type:"Date",Width:100,SaveName:"D",Format:"Ymd",ColMerge:0},
{Header:"시간|시작",Type:"Date",Width:100,Format:"Hm",ColMerge:1,Align:"Center"},
{Header:["시간", "종료"],Type:"Date",Width:100,Format:"Hm",ColMerge:1,Align:"Center"}
];
//초기화
IBS_InitSheet(mySheet, initdata);
```