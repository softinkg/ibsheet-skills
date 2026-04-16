# Down2Excel Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > Down2Excel Method

---

- **기능**

> 조회된 데이터가 있는 경우 IBSheet의 내용을 엑셀 파일로 변환하여 다운로드 한다.
>
> 전달되는 인자의 형식은 JSON 타입으로 설정 하고자 하는 정보를 JSON 형태로 구성하여 전달한다.
>
> 예)
>
> var params = { FileName : "myFile.xls", SheetName : "Sheet"} ;
>
> mySheet.Down2Excel(params);
>
> **AllTypeToText** 인자는 Int, Float를 제외한 모든 컬럼 타입을 Text타입으로 다운로드 받고자 하는 경우에 설정한다.
>
> AllTypeToText 인자를 1로 설정하는 경우 컬럼에 설정한 모든 포맷(Int, Float 제외)은 무시 되며 TextToGeneral의 설정값에 의하여 다운로드 받은 엑셀 서식을 일반 또는 텍스트로 설정한다.
>
> **AppendPrevSheet** 속성은 [Down2ExcelBuffer](#down2excelbuffer-method) 메소드를 이용하여 2개 이상의 시트를 엑셀 파일로 다운로드 할 때 이전의 시트 내용을 작성한 워크시트에 현재의 시트 내용을 Append 하여 작성할지 여부를 설정한다. 설정값이 0(false)인 경우 워크시트를 새로 생성하여 작성되고, 1(true)인 경우 마지막 작성한 워크시트에 Append 하여 작성 된다. Buffer 모드의 첫번째의 시트인 경우와 Buffer 모드설정이 아닌 경우는 해당 속성의 설정값은 무시된다.
>
> **AutoSizeColumn** 인자는 컬럼 넓이를 내용에 맞게 자동으로 조절한다. 단, 자동조절 결과가 정확하게 맞지 않을수 있다.
>
> **CheckBoxOnValue** 인자는 체크박스와 라디오 박스에서 체크를 한 경우 1 값 대신 다른 값을 지정할 수 있다. 기본값 1.
>
> **CheckBoxOffValue** 인자는 체크박스와 라디오 박스에서 체크해제를 한 경우 0 값 대신 다른 값을 지정할 수 있다. 기본값 0.
>
> **ComboValidation** 인자는 콤보 타입의 컬럼에 대하여 데이터영역(헤더, 소계, 누계, 합계행 제외)에 드롭다운 리스트 형식(데이터 유효성 검사)으로 생성할지를 설정한다. 기본값은 0으로 데이터 유효성 검사를 하지 않는다.
>
> 1로 설정시 리스트의 항목은 DownCombo 가 "Code"이면 컬럼에 설정된 ComboCode가 사용되며, "Text"일 경우 ComboText 값을 사용한다.
>
> 셀별로 InitCellProperty 로 변경한 Combo 목록은 엑셀의 드롭다운 리스트 목록에 별개로 적용되지 않으나 엑셀다운시 정상적인 값이 보여진다.
>
> **DownCols** 인자는 다운로드 받을 컬럼들을 "\|" 문자로 연이은 문자열이다. SaveName과 컬럼인덱스가 모두 가능하다. 널인 경우 모든 컬럼의 자료를 다운로드 받는다.
>
> **DownCombo** 인자는 콤보와 콤보에디트의 선택항목을 TEXT 형태와 CODE 형태로 다운로드 받을 수 있다. 기본값은 "TEXT" 이며 "CODE"를 입력하면 TEXT 대신 해당 CODE 로 다운로드 받는다.
>
> **DownHeader** 인자는 헤더를 포함하여 다운로드 받을지 설정한다. 기본값은 1(헤더 포함) 이다.
>
> **DownRows** 인자는 다운로드 받을 행들을 "\|" 문자로 연이은 문자열이다. 널인 경우 모든 행의 자료를 다운로드 받는다. "Visible" 일 경우 숨겨진 행을 제외한 현재 보여지는 행만 다운 받는다. 널이 아닐경우 **DownTreeHide** 인자는 false 로 설정됩니다.
>
> **DownSum** 인자는 합계를 포함하여 다운로드 받을지 설정한다. 기본값은 1(합계 포함) 이다.
>
> **DownTreeHide** 인자는 트리의 접혀진 행을 다운 받을 때 사용한다.
>
> True 일경우 SetRowHidden 으로 숨긴 로우도 모두 다운 받는다.
>
> **ExcelFontSize** 인자는 SheetFontSize 와는 별개로 엑셀문서에서만 특정 폰트 크기로 지정할 수 있다.
>
> **ExcelHeaderRowHeight** 인자는 엑셀문서에서만 헤더 행을 특정 픽셀 크기로 지정하기 위하여 사용한다.
>
> **ExcelRowHeight** 인자는 엑셀문서에서만 모든 행을 특정 픽셀 크기로 지정하기 위하여 사용한다. "auto"로 설정할 경우 자동으로 행 높이를 설정한다.
>
> **ExcludeSubSum** 인자는 다운 받는 행중에서 소계/누계 행을 제외하고 싶을 때 설정한다.
>
> **ExtendParam** 인자는 서버로 전달해야 하는 내용이 있는 경우 Get방식의 QueryString으로 연결하여 설정하면 URL에 지정한 페이지로 같이 전달 된다.
>
> 예제)
>
> param = { ExtendParam:"**sawon_name=shkim&sawon_no=12345**",
>
> URL:"/ibsheet7_down2excel_extendparam/fp.jsp };
>
> **ExtendParamMethod** 인자는 ExtendParam 의 내용을 GET 또는 POST 로 전달할지를 설정한다.
>
> **FileName** 인자는 엑셀 다운로드시 파일명을 설정한다. 파일 확장자를 xls 로 지정시 엑셀 2003 포맷으로 다운로드하고, xlsx 로 지정시 엑셀 2007 포맷으로 다운로드하며, 확장자를 지정하지 않을경우에는 xls 포맷으로 다운로드 받는다.
>
> **FreezePane** 인자는 엑셀 다운로드시 틀고정을 설정한다. 데이터를 서버로 전송하여 다운로드 하는 경우 jar 이름이 ibsheet7-2~.jar로 되어 있어야 지원 가능하다.  
> 설정값 : 1(헤더의 Row 고정) , 2(컬럼 고정) ,
>
> 3(헤더의 Row + 컬럼 고정), 4(FrozenRow 함수로 설정한 값 고정),
>
> 5(FrozenRow 함수로 설정한 값 + 컬럼 고정)
>
> **HiddenColumn** 인자는 숨은 컬럼들을 엑셀로 다운로드 받은 경우, 해당 컬럼이 눈에 보이지는 않지만 엑셀 메뉴중 "숨기기 취소"를 선택한 경우 해당 컬럼이 다시 보일 수 있도록 엑셀 문서에 다운로드 받는다.
>
> **KeyFieldMark** 인자는 KeyField 컬럼의 KeyField 마크(\*)를 다운 받을 때 사용한다.
>
> **Merge** 인자는 IBSheet의 머지 상태를 엑셀문서에 그대로 반영할지를 설정한다. 이 인자를 사용하는 경우 처리 속도가 더 느릴 수 있다. 기본값은 0(머지 반영 안함) 이다. 설정이 가능한 값은 아래와 같다

| 설정값 | 설명                                           |
|:------:|------------------------------------------------|
|   0    | 사용 안함                                      |
|   1    | 사용함 (셀 병합시 부속셀의 값 설정 함)         |
|   2    | 사용함 (셀 병합시 부속셀의 값은 설정하지 않음) |

> *※ 소계, 누계가 있는 시트의 경우 머지처리가 안됨.*
>
> *※ 머지 적용 처리는 [Appendix#4. 엑셀 다운시 머지 적용 처리](#엑셀-다운시-머지-적용-처리) 참조*
>
> **NumberFormatMode** 속성은 실수 형태의 데이터타입에 대한 셀서식 설정 방식을 설정할 때 사용 한다. 설정값에 따른 처리 방식은 아래와 같다.

| 설정값 | 내용                                                      |
|:------:|-----------------------------------------------------------|
|   0    | 컬럼 단위 Format 기준 셀서식 설정                         |
|   1    | 셀의 값 기준에 따라 정수 또는 실수 포맷형태의 셀서식 설정 |
|   2    | 일반 서식으로 설정 (별도의 셀 서식포맷을 설정하지 않음)   |

> **OnlyHeaderMerge** 인자는 데이터영역의 머지를 강제로 제한하여 속도를 개선할 때 사용한다.
>
> **PrintSetup** 인자는 엑셀파일을 다운로드할 때 프린트에 대한 설정 기능을 할때 사용한다.

| Parameter | Type | 필수 여부 | 내용 |
|:--:|:--:|:--:|----|
| PageSize | String | 선택 | 용지 사이즈를 설정(A4, B4..) |
| LandScape | Boolean | 선택 | 용지 방향을 설정, true는 가로, false는 세로 |
| AutoBreak | Boolean | 선택 | 페이지를 나눌 때 셀이 잘리지 않도록 설정 |
| FitToPage | Boolean | 선택 | 용지 내에 페이지를 맞춰서 인쇄할 지 여부 설정 |
| FitWidth | Boolean | 선택 | 페이지 내에 열 맞춤 설정, true로 설정 시 FittoPage(true); 와 FitHeight(false); 를 함께 설정 |
| FitHeight | Boolean | 선택 | 페이지 내에 행 맞춤 설정, true로 설정 시 FittoPage(true); 와 FitWidth(false); 를 함께 설정 |
| ColorPrint | Boolean | 선택 | 컬러 인쇄 여부를 설정, 기본값은 true이고 false로 설정하면 흑백인쇄 모드 |
| TopMargin | Number | 선택 | 위쪽 여백을 cm 단위로 설정 |
| BottomMargin | Number | 선택 | 아래쪽 여백을 cm 단위로 설정 |
| HeaderMargin | Number | 선택 | 머리글 부분의 여백을 cm 단위로 설정 |
| FooterMargin | Number | 선택 | 꼬리글 부분의 여백을 cm 단위로 설정 |
| LeftMargin | Number | 선택 | 왼쪽 여백을 cm 단위로 설정 |
| RightMargin | Number | 선택 | 오른쪽 여백을 cm 단위로 설정 |

> **ReportXMLURL** 특정 xml로 부터 엑셀파일에 설정할 머릿글,바닥글 등을 설정한다. Xml 파일에 대한 자세한 내용은 6.4장의 "**엑셀리포트 XML**"부분을 참고
>
> **ReqHeader** Request Header에 사용자가 지정한 헤더 정보를 설정한다.
>
> 이 인자를 설정하게 되면 UseXhr : true한 것과 같은 방식으로 동작한다.
>
> **SheetDesign** 인자는 IBSheet 의 디자인을 반영한다. 폰트명, 폰트크기, 배경색등을 지원하고 있다. 이 인자를 사용하는 경우 처리 속도가 더 느릴 수 있다. 기본값은 0(디자인 반영 안함)이다. 폰트색은 항상 검은색만 표시되며 다양한 폰트 색상의 반영을 지원하지 않는다. 셀 배경색은 1개의 엑셀파일 문서 내에서 최대 48가지의 동시 색상만을 지원한다. 따라서, 그 이상의 더 다양한 색상이 1개의 IBSheet 내에 포함된 경우에는 기존 48가지 셀색상들중 가장 유사한 색상으로 대체 표현됨을 유의하여야 한다. 2로 설정한 경우 1 설정과 같이 디자인은 반영하되 셀 테두리는 그리지 않는다. 3으로 설정한 경우 셀 테두리 및 디자인을 모두 반영하지 않는다.
>
> **SheetName** 인자는 엑셀에 WorkSheet 이름을 설정하는것으로 데이터 양이 많아서 1개 WorkSheet에 내릴수 있는 최대 행의 개수인 65536개를 초과할 경우 원래 이름과 중복 사용할수 없으므로 이름 뒤에 괄호와 인덱스가 붙는다. 예를 들어 "1월"이라고 설정했다면 초과된 데이터는 새로운 WorkSheet에 "1월(1)", "1월(2)"라고 이름을 표시한다.
>
> **TempFile** 인자는 템플릿으로 사용할 엑셀 파일을 서버에 두고 해당 파일에 시트 데이터만 삽입하여 다운로드할때 사용하는 속성으로 템플릿으로 사용할 엑셀 파일명을 지정한다. 템플릿 기능을 사용하는 경우 Down2Excel.jsp 파일 내에 TempRoot설정(사용자 환경 설정 \#9) 이 되어 있어야 하며 템플릿 파일의 경로가 맞지 않는 경우 SheetDesign을 0으로 설정한 상태로 일반 다운로드 처리된다. StartRow, StartCol 인자를 통해 템플릿 파일에서 데이터를 쓰기 시작할 위치를 설정 할 수 있으며 템플릿 파일에서 데이터를 쓸 WorkSheet를 SheetName 또는 SheetNo로 설정할 수 있다.
>
> SheetName을 설정한 경우 SheetNo보다 우선하며 유효하지 않은 값인 경우 SheetNo 설정값으로 처리된다.
>
> 템플릿 다운로드를 사용하는 경우 모든 서식/디자인은 템플릿 파일에 설정된것을 사용하므로 ExcelFontSize, ExcelRowHeight, SheetDesign,ReportXMLURL 속성이 무시된다.
>
> 주의) 템플릿 파일에 날짜타입, 숫자 타입등의 서식 설정이 다운하고자 하는 시트 데이터 타입과 다르게 설정된 경우 데이터 값이 다르게 출력될 수 있다.
>
> **TextToGeneral** 인자는 IBSheet 의 컬럼이 Text Type 일 경우 엑셀로 다운되었을때 일반 또는 텍스트 서식(엑셀의 셀 서식)으로 변경할 때 사용한다.
>
> **TitleAlign** 인자는 TitleText로 설정한 제목이나 기타 내용에 대한 정렬을 설정한다. "left", "center", "right" 중 원하는 값으로 설정 가능하며 별도 설정하지 않는 경우 기본값인 "center"로 처리된다.
>
> **TitleText** 인자는 그리드의 위쪽에 제목이나 기타 자료들을 사용자의 임의대로 넣을 수 있는 기능이다. A\|B\|C\r\nD\|E\|F 와 같이 입력한 경우 첫 행에 3개의 셀에 각각 A,B,C 값이 들어가고 두번째 행의 3개의 셀에 각각 D,E,F 값이 들어간다. 값 안에서 엔터를 포함하려면 \r 이나 \n 을 삽입하도록 한다. \r\n 이 10개가 포함되면 11줄을 차지하게 되고 12번째 행부터 IBSheet 자료가 이어진다.
>
> 이 인자에 넣은 셀자료들은 엑셀에 표시된 컬럼 수보다 더 많은 컬럼의 자료를 넣을 경우 그 값들은 무시된다. 즉 엑셀다운에 표시되는 컬럼이 모두 10개의 컬럼이면 타이틀이나 기타 자료들을 최대 10개까지만 가능하므로 11개 이상의 자료를 넣을 수는 없다. (타이틀 행의 제한은 별도로 없음)
>
> **TreeLevel** 인자는 트리구조 컬럼의 트리 레벨을 다운 받을 때 사용한다.
>
> **URL** 인자는 Down2Excel과 더불어 서버에서 처리해야 하는 내용이 있는 경우,(가령 로그를 남긴다거나) 로직을 처리할 URL을 넣어주면 Down2Excel.jsp 페이지를 호출하기 전에 먼저 URL인자에서 설정한 페이지를 호출한다. 따라서 설정 페이지에서는 작업이 끝난 후, request를 Down2Excel.jsp 페이지로 전달하여야 한다.
>
> 예제)
>
> var param = { [URL:"/ibsheet7_down2excel_extendparam/fp.jsp](file:///D:\project\ibsheet7-manual2md\20200206\%22\ibsheet7_down2excel_extendparam\fp.jsp)"};
>
> mySheet.Down2Excel(param);
>
> 서버쪽 페이지)
>
> RequestDispatcherrd= request.getRequestDispatcher("/ibsheet7_down2excel_extendparam/IBSheet/Down2Excel.jsp");
>
> rd.forward(request,response);
>
> **UserMerge** 인자는 TitleText 로 입력한 셀별 자료들이나 IBSheet에 해당되는 셀 자료들을 임의로 머지 적용하기 위하여 설정한다. 1개의 머지문은 4개의 숫자와 콤마로 조합되며 여러 개의 머지는 공백(스페이스) 문자로 조합된다. "0,0,2,2 2,0,1,8" 과 같이 설정한 경우 엑셀의 첫행, 첫열인 (0,0)에서 2x2 크기의 머지가 하나 적용되고 2행, 0열의 셀인(2, 0) 에서 1x8 크기의 머지가 하나 더 적용된다.
>
> **UseXhr** 인자는 다운로드시 통신 방식을 xhr로 설정하는 인자이다.
>
> 기존 다운로드는 iframe를 통한 form submit 방식으로 동작하였다.
>
> 프레임웍의 각종 보안처리로 인하여 iframe를 사용할 수 없다거나 Cookie(파일 다운로드 완료 후 화면의 대기이미지 닫을 때 필요)를 읽고 쓸수 없을 때 이 속성을 true로 설정하면 된다.
>
> **WordWrap** 인자는 텍스트 셀의 줄바꿈을 허용할지를 설정한다.

- **Syntax**

|        |                                      |
|:------:|--------------------------------------|
| Syntax | ObjId.**Down2Excel**([parameters]) |

- **Info**

| Parameter            | Type    | 필수여부 | 설 명                                                                                                                                    |
| -------------------- | ------- | ---- | -------------------------------------------------------------------------------------------------------------------------------------- |
| AllTypeToText        | Boolean | 선택   | 날짜 데이터를 날짜 서식으로 다운로드 받을지 여부 Default=0                                                                                                  |
| AppendPrevSheet      | Boolean | 선택   | Buffer 모드 사용시 이전 워크시트에 Append 적용 여부 (Default=0)                                                                                        |
| AutoSizeColumn       | Boolean | 선택   | Default=0(컬럼 넓이 자동 조절 안함)                                                                                                              |
| CheckBoxOffValue     | String  | 선택   | 체크박스의 체크 해제시의 값 Default="0"                                                                                                            |
| CheckBoxOnValue      | String  | 선택   | 체크박스의 체크시의 값 Default="1"                                                                                                               |
| ComboValidation      | Boolean | 선택   | 콤보의 드롭다운 형식 다운로드 여부 Defualt=0                                                                                                          |
| DownCols             | String  | 선택   | 다운로드 받을 열들을 \| 로 연결. Default=""(모두 받음)                                                                                                 |
| DownCombo            | String  | 선택   | 콤보의 TEXT/CODE 형태의 다운로드 여부 Default="TEXT"                                                                                               |
| DownHeader           | Boolean | 선택   | 헤더의 다운로드 여부 Default=1                                                                                                                  |
| DownRows             | String  | 선택   | 다운로드 받을 행들을 \| 로 연결. Default=""(모두 받음)                                                                                                 |
| DownSum              | Boolean | 선택   | 합계의 다운로드 여부 Default=1                                                                                                                  |
| DownTreeHide         | Boolean | 선택   | 트리의 접혀진 행 다운 여부 Default=0(다운 안받음)                                                                                                      |
| ExcelFontSize        | Number  | 선택   | 폰트 크기 설정 Default=0                                                                                                                     |
| ExcelHeaderRowHeight | String  | 선택   | 헤더 높이 설정 Default=”” (사용안함)                                                                                                             |
| ExcelRowHeight       | String  | 선택   | Default=""(사용안함)                                                                                                                       |
| ExcludeSubSum        | Number  | 선택   | 소계/누계 행 제외 여부 1: 소계만 제외 2: 누계만 제외 3: 소계/누계 모두 제외 Default=0(소계/누계 모두 포함)                                                                |
| ExcludeFooterRow     | Boolean | 선택   | 푸터 행 제외 여부 1: 제외 0: 제외 안함 Default=0                                                                                                    |
| ExtendParam          | String  | 선택   | Default=""(사용안함)                                                                                                                       |
| ExtendParamMethod    | String  | 선택   | Default="GET"                                                                                                                          |
| FileName             | String  | 선택   | 저장할 파일 명 Default="Excel.xls"                                                                                                           |
| FreezePane           | String  | 선택   | 틀고정 설정 Default=""(사용안함)                                                                                                                |
| HiddenColumn         | Boolean | 선택   | 열숨김 반영 여부. Default=0                                                                                                                   |
| KeyFieldMark         | Boolean | 선택   | KeyField 마크(*)를 다운 여부 Default=1(다운 받음)                                                                                                 |
| Mode                 | Number  | 선택   | 다운로드 모드 -1: Status, Delcheck, Result 타입 및 Hidden 칼럼을 제외하고 다운로드 0: 모든 컬럼을 다운로드 1: Status, DelCheck 타입을 제외하고 다운로드 2: Hidden컬럼을 제외하고 다운로드 |
| Merge                | Number  | 선택   | 머지의 다운로드 적용 방식 설정 (Default=0)                                                                                                          |
| NumberExMode         | Boolean | 선택   | 시트의 숫자 컬럼 포맷을 숫자 서식으로 내려받을지 여부. 기존에는 숫자 컬럼이 포맷에 따라 통화나 사용자 지정 서식으로 다운됨. (Default=0)                                                    |
| NumberFormatMode     | Number  | 선택   | 실수 형태의 데이터 타입에 대한 셀서식 설정 방식 설정 (Default=0)                                                                                             |
| NumberTypeToText     | Boolean | 선택   | 숫자타입 셀 데이터를 문자 타입으로 다운로드 받을지 여부. 숫자타입 컬럼의 일부 셀에 포맷을 변경하여 문자열을 삽입하는 경우 사용 Default=0                                                     |
| OnlyHeaderMerge      | Boolean | 선택   | 헤더만 머지할지의 여부 Default=0                                                                                                                 |
| PrintSetup           | Object  | 선택   | 엑셀파일을 다운로드할 때 프린트에 대한 설정 기능 사용 여부                                                                                                      |
| ReportXMLURL         | String  | 선택   | 엑셀파일에 타이틀이나 패턴등을 별도의 xml파일을 통해 설정                                                                                                      |
| ReqHeader            | Object  | 선택   | Request Header에 값 설정                                                                                                                   |
| SheetDesign          | Number  | 선택   | 디자인 다운로드 적용 여부 Default=0                                                                                                               |
| SheetName            | String  | 선택   | 엑셀WorkSheet이름, Default="Sheet"                                                                                                         |
| SheetNo              | Number  | 선택   | 템플릿으로 사용할 엑셀 WorkSheet 번호. Default=0                                                                                                   |
| StartCol             | Number  | 선택   | 템플릿 적용 다운로드 시 엑셀 파일내 데이터를 쓰기 시작할 컬럼 번호 Default=0                                                                                       |
| StartRow             | Number  | 선택   | 템플릿 적용 다운로드 시 엑셀 파일내 데이터를 쓰기 시작할 행 번호 Default=0                                                                                        |
| TempFile             | String  | 선택   | 템플릿으로 사용할 엑셀 파일명파일명                                                                                                                    |
| TextToGeneral        | Boolean | 선택   | Type:”Text”의 엑셀 서식 형식 Default=1(일반)                                                                                                    |
| TitleAlign           | String  | 선택   | Default="center"(중앙정렬)                                                                                                                 |
| TitleText            | String  | 선택   | Default=""(사용안함)                                                                                                                       |
| TreeLevel            | Boolean | 선택   | Default=0(다운 안받음)                                                                                                                      |
| URL                  | String  | 선택   | Default=""(사용안함)                                                                                                                       |
| UserMerge            | String  | 선택   | Default=""(사용안함)                                                                                                                       |
| UseXhr               | Boolean | 선택   | xhr 통신을 이용해 엑셀 파일을 다운로드 Default=false                                                                                                  |
| WordWrap             | Boolean | 선택   | Default=1(줄바꿈 허용)                                                                                                                      |

- **Example**

```javascript
// 엑셀로 내려 받기
mySheet.Down2Excel();
// 다운로드할 파일명을 excel2로 하고 워크시트명은 sheet-test 로 정의하여다운로드 받는다.
mySheet.Down2Excel({FileName:'excel2',SheetName:' sheet-test'});
//시트 색상과 머지를 모두 반영하며, 콤보는 코드로, 체크는 Y/N으로 다운로드 받되,헤더와 합계는 제외하고 컬럼은 왼쪽에서 3개의 컬럼만 다운로드 한다.
mySheet.Down2Excel({SheetDesign:1, Merge:1, DownCombo:'CODE', CheckBoxOnValue:'Y', CheckBoxOffValue:'N', DownRows:'', DownCols:'0|1|2', DownHeader:0, DownSum:0});
//xhr 통신
mySheet.Down2Excel({UseXhr:true,FileName:'excel2',SheetName:' sheet-test'});
mySheet.Down2Excel({ReqHeader:{ "IBLeaders":"IBSheet"},
FileName:'excel2',SheetName:' sheet-test'});
```

- **제공 버전**

| **7.0.0.0**    |                                                                            |
| -------------- | -------------------------------------------------------------------------- |
| **7.0.2.0**    | AllTypeToText 속성 추가                                                        |
| **7.0.13.11**  | AppendPrevSheet 속성 추가                                                      |
| **7.0.13.12**  | Merge 속성 타입 변경                                                             |
| **7.0.13.26**  | NumberFormatMode 속성 추가                                                     |
| **7.0.13.89**  | Mode 속성 추가                                                                 |
| **7.0.13.94**  | NumberExMode 속성 추가                                                         |
| **7.0.13.110** | ExcelHeaderRowHeight 속성 추가                                                 |
| **7.0.13.111** | PrintSetup 속성 추가                                                           |
| **7.0.13.121** | ExcludeFooterRow 속성 추가                                                     |
| **7.0.13.218** | FreezePane 속성 추가 클라이언트 모듈 : 7.0.0.37-20230511-16 서버모듈 : ibsheet7-2.1.6.jar |
| **7.0.13.230** | ReqHeader, UseXhr 속성 추가                                                    |

**  **