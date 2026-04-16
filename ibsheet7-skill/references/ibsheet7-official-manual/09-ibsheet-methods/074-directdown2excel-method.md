# DirectDown2Excel Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DirectDown2Excel Method

---

- **기능**

> 조회된 데이터가 많은 경우 Down2Excel()메서드를 이용하여 엑셀 파일을 다운로드 하면 client에서 조회된 데이터를 서버로 보내는 과정에서 상당한 부하가 걸릴수 있다.
>
> 따라서 client의 아이비시트로부터는 헤더타이틀이나 각 컬럼의 서식(포멧)정보만 서버로 전달하고, 데이터부분은 별도의 페이지(혹은 서블릿)을 통해 데이터를 java.util.List (java.util.Map) 구조로 생성하여 "SHEETDATA"라는 이름으로 request객체에 담아 DirectDown2Excel.jsp파일에 전달하면 client로 부터온 해더정보와 디비의 데이터를 조합하여 엑셀 파일을 생성 다운로드 하는 메서드 이다.
>
> 처리되는 과정은 다음과 같다.
>
> 

```javascript
// 화면 페이지
var cols = [
{Type:"Text",Width:85,SaveName:"POSTNO",Format:"PostNo",Align:"center"},
{Type:"Text",Width:70,SaveName:"SIDO"},
{Type:"Text",Width:80,SaveName:"SIGUNGU"},
{Type:"Text",Width:80,SaveName:"LEE"},
{Type:"Text",Width:300,SaveName:"ADDRESS"}
];
mySheet.InitColumns(cols);
var param = {
URL:"/bus/bussinessList.jsp" //비지니스 로직 페이지
,ExtendParam:"sa_nm=양진열&sa_no=980123"
,FileName:"PersonList.xls"
};
//시트에 조회된 데이터는 전달되지 않고, 헤더타이틀이나 컬럼의 포멧 만 서버로 전달됨.
Sheet.DirectDown2Excel(param);
```

```
// bussinessList.jsp 페이지
// 1. 화면으로 부터 조회 조건을 받음.

String sa_name = request.getParameter("sa_nm");
String sa_no = request.getParameter("sa_no');
// 2. 엑셀로 내려질 데이터를 DB에서 조회
String query
= "SELECT POSTNO, SIDO, SIGUNGU, LEE, ADDRESS FROM POSTNO";
Class.forName(driver);
conn = DriverManager.getConnection(url,id,pwd);
pstmt = conn.prepareStatement(query);
rs = pstmt.executeQuery();
// 3. 데이터를 List(Map)형태로 전환.
Java.util.List li = new java.util.List();
java.util.Map mp = null;
while(rs.next()){
mp = new Java.util.Map();
//map 데이터 생성시 이름은 반드시 시트의 SaveName과 동일해야 한다.
Mp.put("POSTNO",rs.getString("POSTNO"));
mp.put("SIDO",rs.getString("SIDO"));
..
..
li.add(mp);
}
// 데이터를 반드시 SHEETDATA라는 이름으로 담는다.
Request.setAttribute("SHEETDATA", li);
// 4. DirectDown2Excel.jsp 페이지로 forwarding
System.out.println("전체 건수:"+li.size());
String forwardPath = "./DirectDown2Excel.jsp";
if(!"".equals(forwardPath)){
RequestDispatcher rd = request.getRequestDispatcher(forwardPath);
rd.forward(request,response);
}
```

> 전달되는 인자의 형식은 JSON 타입으로 설정 하고자 하는 정보를 JSON 형태로 구성하여 전달한다.
>
> 예)
>
> var params = { FileName : "myFile.xls", SheetName : "Sheet"} ;
>
> **AllTypeToText** 인자는 Int, Float를 제외한 모든 컬럼 타입을 Text타입으로 다운로드 받고자 하는 경우에 설정한다.
>
> AllTypeToText 인자를 1로 설정하는 경우 컬럼에 설정한 모든 포맷(Int, Float 제외)은 무시 되며 TextToGeneral의 설정값에 의하여 다운로드 받은 엑셀 서식을 일반 또는 텍스트로 설정한다.
>
> **AppendPrevSheet** 속성은 [Down2ExcelBuffer](#down2excelbuffer-method) 메소드를 이용하여 2개 이상의 시트를 엑셀 파일로 다운로드 할 때 이전의 시트 내용을 작성한 워크시트에 현재의 시트 내용을 Append 하여 작성할지 여부를 설정한다. 설정값이 0(false)인 경우 워크시트를 새로 생성하여 작성되고, 1(true)인 경우 마지막 작성한 워크시트에 Append 하여 작성 된다. Buffer 모드의 첫번째의 시트인 경우와 Buffer 모드설정이 아닌 경우는 해당 속성의 설정값은 무시된다.
>
> **AutoSizeColumn** 인자는 컬럼 너비를 내용에 맞게 자동으로 조절한다. 단, 자동조절 결과가 정확하게 맞지 않을수 있다.
>
> **ComboValidation** 인자는 콤보 타입의 컬럼에 대하여 데이터영역(헤더, 소계, 누계, 합계행 제외)에 드롭다운 리스트 형식(데이터 유효성 검사)으로 생성할지를 설정한다. 기본값은 0으로 데이터 유효성 검사를 하지 않는다.
>
> 1로 설정시 리스트의 항목은 DownCombo 가 "Code"이면 컬럼에 설정된 ComboCode가 사용되며, "Text"일 경우 ComboText 값을 사용한다.
>
> 셀별로 InitCellProperty 로 변경한 Combo 목록은 엑셀의 드롭다운 리스트 목록에 별개로 적용되지 않으나 엑셀다운시 정상적인 값이 보여진다.
>
> **DownCols** 인자는 다운로드 받을 컬럼들을 "\|" 문자로 연이은 문자열이다.
>
> SaveName과 컬럼인덱스가 모두 가능하다. 널인 경우 모든 컬럼의 자료를 다운로드 받는다.
>
> **DownCombo** 인자는 콤보와 콤보에디트의 선택항목을 TEXT 형태와 CODE 형태로 다운로드 받을 수 있다. 기본값은 "TEXT" 이며 "CODE"를 입력하면 TEXT 대신 해당 CODE 로 다운로드 받는다.
>
> **DownHeader** 인자는 헤더를 포함하여 다운로드 받을지 설정한다. 기본값은 1(헤더 포함) 이다.
>
> **ExcelFontSize** 인자는 SheetFontSize 와는 별개로 엑셀문서에서만 특정 폰트 크기로 지정할 수 있다.
>
> **ExcelHeaderRowHeight** 인자는 엑셀문서에서만 헤더 행을 특정 픽셀 크기로 지정하기 위하여 사용한다.
>
> **ExcelRowHeight** 인자는 엑셀문서에서만 모든 행을 특정 픽셀 크기로 지정하기 위하여 사용한다. "auto"로 설정할 경우 자동으로 행 높이를 설정한다.
>
> **ExtendParam** 인자는 서버측으로 전달할 조회조건등의 내용을 Get 방식의QueryString을 만들어 넣어주면 URL인자로 지정한 페이지에서 request.getParameter() 메서드를 통해 받아 볼 수 있다.
>
> Ex) ExtendParam:"name=shkim&sa_no=980123&enter_date=19980222";
>
> **ExtendParamMethod** 인자는 ExtendParam 의 내용을 GET 또는 POST 로 전달할지를 설정한다.
>
> **FileName** 인자는 엑셀 다운로드시의 파일명을 설정한다. 파일 확장자를 xls 로 지정시 엑셀 2003 포맷으로 다운로드하고, xlsx 로 지정시 엑셀 2007 포맷으로 다운로드하며, 확장자를 지정하지 않을경우에는 xls 포맷으로 다운로드 받는다.
>
> Ex ) FileName:"NameCard.xls"
>
> **HiddenColumn** 인자는 숨은 컬럼들을 엑셀로 다운로드 받은 경우, 해당 컬럼이 눈에 보이지는 않지만 엑셀 메뉴중 "숨기기 취소"를 선택한 경우 해당 컬럼이 다시 보일 수 있도록 엑셀 문서에 다운로드 받는다.
>
> **KeyFieldMark** 인자는 KeyField 컬럼의 KeyField 마크(\*)를 다운 받을 때 사용한다.
>
> **Merge** 인자는 헤더 데이터에 인접한 셀간에 같은 글자가 있는 경우, 병합할 지 여부를 결정한다. 기본값 0 이다.
>
> **Multipart** 인자는 시트의 헤더 정보를 서버로 전달할 경우 Multipart 형식인지 아니면 일반 형식으로 전달할 것인지를 결정한다. (Spring,struts2 등의 프레임웍 사용시 반드시 사용할 것)
>
> IBSheet는 excel export 기능과 관련하여 서버로 데이터를 전달시 기본적으로 Multipart 형식으로 전달한다. 이는 시트위에 데이터가 많아서 일반적인 post 형식으로 전달할 경우 서버에서 받지 못하는 것을 방지하기 위함이다. 하지만 DirectDown2Excel메서드와 spring 프레임웍을 사용하는 경우 먼저 데이터를 스프링 프레임웍으로 부터 얻게 되는데, 이때 프레임웍에서 Multipart 데이터를 모두 가져가 실제 forwarding을 받는 DirectDown2Excel.jsp 에서는 시트의 헤더정보을 얻지 못하게 된다. 따라서 spring 프레임웍을 사용시에는 이 인자를 0(false)로 설정하고, DirectDown2Excel.jsp 파일에서 헤더 정보를 얻는 아래 부분을 다음과 같이 수정하여 야 한다.
>
> [DirectDown2Excel.jsp 내용]

```
// 파라메터 정보를 얻음
String data = ibExcel.getData();
위 내용을 아래와 같이 수정
String data = request.getParameter("Data");
```

> **NumberFormatMode** 속성은 실수 형태의 데이터타입에 대한 셀서식 설정 방식을 설정할 때 사용 한다. 설정값에 따른 처리 방식은 아래와 같다.

| 설정값 | 내용                                                      |
|:------:|-----------------------------------------------------------|
|   0    | 컬럼 단위 Format 기준 셀서식 설정                         |
|   1    | 셀의 값 기준에 따라 정수 또는 실수 포맷형태의 셀서식 설정 |
|   2    | 일반 서식으로 설정 (별도의 셀 서식포맷을 설정하지 않음)   |

> **NumberTypeToText** 인자는 숫자타입 셀 데이터를 문자 타입으로 다운로드 받을때 사용한다.
>
> TextToGeneral의 설정값에 의하여 다운로드 받은 엑셀 서식을 일반 또는 텍스트로 설정한다. 기본값은 0 이다.
>
> **ReportXMLURL** 특정 xml로 부터 엑셀파일에 설정할 머릿글,바닥글 등을 설정한다. Xml 파일에 대한 자세한 내용은 6.4장의 "**엑셀리포트 XML**"부분을 참고
>
> **ReqHeader** Request Header에 사용자가 지정한 헤더 정보를 설정한다..  
> 이 인자를 설정하게 되면 UseXhr : true한 것과 같은 방식으로 동작한다.
>
> **SheetDesign** 인자는 헤더의 색상을 반영할지 여부를 결정한다. 기본값은 0이다.
>
> **SheetName** 인자는 엑셀에 WorkSheet 이름을 설정하는것으로 데이터 양이 많아서 1개 WorkSheet에 내릴수 있는 최대 행의 개수인 65536개를 초과할 경우 원래 이름과 중복 사용할수 없으므로 이름 뒤에 괄호와 인덱스가 붙는다. 예를 들어 "1월"이라고 설정했다면 초과된 데이터는 새로운 WorkSheet에 "1월(1)", "1월(2)"라고 이름을 표시한다
>
> ex) SheetName:"SupportTeam"
>
> **TextToGeneral** 인자는 IBSheet 의 컬럼이 Text Type 일 경우 엑셀로 다운되었을때 일반 또는 텍스트 서식(엑셀의 셀 서식)으로 변경할 때 사용한다.
>
> **TitleAlign** 인자는 TitleText로 설정한 제목이나 기타 내용에 대한 정렬을 설정한다. "left", "center", "right" 중 원하는 값으로 설정 가능하며 별도 설정하지 않는 경우 기본값인 "center"로 처리된다.
>
> **TitleText** 인자는 그리드의 위쪽에 제목이나 기타 자료들을 사용자의 임의대로 넣을 수 있는 기능이다. A\|B\|C\r\nD\|E\|F 와 같이 입력한 경우 첫 행에 3개의 셀에 각각 A,B,C 값이 들어가고 두번째 행의 3개의 셀에 각각 D,E,F 값이 들어간다. 값 안에서 엔터를 포함하려면 \r 이나 \n 을 삽입하도록 한다. \r\n 이 10개가 포함되면 11줄을 차지하게 되고 12번째 행부터 IBSheet 자료가 이어진다.
>
> 이 인자에 넣은 셀자료들은 엑셀에 표시된 컬럼 수보다 더 많은 컬럼의 자료를 넣을 경우 그 값들은 무시된다. 즉 엑셀다운에 표시되는 컬럼이 모두 10개의 컬럼이면 타이틀이나 기타 자료들을 최대 10개까지만 가능하므로 11개 이상의 자료를 넣을 수는 없다. (타이틀 행의 제한은 별도로 없음)
>
> **URL** 인자는 엑셀보여질 데이터를 생성할 페이지에 대한 경로를 넣는다.(**필수**)
>
> ex) [URL:"/bus/displayList.do](file:///D:\project\ibsheet7-manual2md\20200206\%22\bus\displayList.do)"
>
> **UserMerge** 인자는 TitleText 로 입력한 셀별 자료들이나 IBSheet에 해당되는 셀 자료들을 임의로 머지 적용하기 위하여 설정한다. 1개의 머지문은 4개의 숫자와 콤마로 조합되며 여러 개의 머지는 공백(스페이스) 문자로 조합된다. "0,0,2,2 2,0,1,8" 과 같이 설정한 경우 엑셀의 첫행, 첫열인 (0,0)에서 2x2 크기의 머지가 하나 적용되고 2행, 2열의 셀인(2,0) 에서 1x8 크기의 머지가 하나 더 적용된다.
>
> **UseXhr** 인자는 다운로드시 통신 방식을 xhr로 설정하는 인자이다.  
> 기존 다운로드는 iframe를 통한 form submit 방식으로 동작하였다.  
> 프레임웍의 각종 보안처리로 인하여 iframe를 사용할 수 없거나 Cookie(파일 다운로드 완료 후 화면의 대기이미지 닫을 때 필요)를 읽고 쓸수 없을 때 이 속성을 true로 설정하면 된다.

- **Syntax**

|        |                                            |
|:------:|--------------------------------------------|
| Syntax | ObjId.**DirectDown2Excel**([parameters]) |

- **Info**

| Parameter            | Type    | 필수여부 | 설 명                                                                                                                                    |
| -------------------- | ------- | ---- | -------------------------------------------------------------------------------------------------------------------------------------- |
| AllTypeToText        | Boolean | 선택   | 날짜 데이터를 날짜 서식으로 다운로드 받을지 여부 Default=0                                                                                                  |
| AppendPrevSheet      | Boolean | 선택   | Buffer 모드 사용시 이전 워크시트에 Append 적용 여부 (Default=0)                                                                                        |
| AutoSizeColumn       | Boolean | 선택   | Default=0(컬럼 넓이 자동 조절 안함)                                                                                                              |
| ComboValidation      | Boolean | 선택   | 콤보의 드롭다운 형식 다운로드 여부 Defualt=0                                                                                                          |
| DownCols             | String  | 선택   | 다운로드 받을 열들을 \| 로 연결. Default=""(모두 받음)                                                                                                 |
| DownCombo            | String  | 선택   | 콤보의 TEXT/CODE 형태의 다운로드 여부 Default="TEXT"                                                                                               |
| DownHeader           | Boolean | 선택   | 헤더의 다운로드 여부 Default=1                                                                                                                  |
| ExcelFontSize        | Number  | 선택   | 폰트 크기 설정 Default=0                                                                                                                     |
| ExcelHeaderRowHeight | String  | 선택   | 헤더 높이 설정 Default=”” (사용안함)                                                                                                             |
| ExcelRowHeight       | String  | 선택   | Default=""(사용안함)                                                                                                                       |
| ExtendParam          | String  | 선택   | Default=""(사용안함)                                                                                                                       |
| ExtendParamMethod    | String  | 선택   | Default="GET"                                                                                                                          |
| FileName             | String  | 선택   | 저장할 파일 명 Default="Excel.xls"                                                                                                           |
| HiddenColumn         | Boolean | 선택   | 열숨김 반영 여부. Default=0                                                                                                                   |
| KeyFieldMark         | Boolean | 선택   | KeyField 마크(*)를 다운 여부 Default=1(다운 받음)                                                                                                 |
| Mode                 | Number  | 선택   | 다운로드 모드 -1: Status, Delcheck, Result 타입 및 Hidden 칼럼을 제외하고 다운로드 0: 모든 컬럼을 다운로드 1: Status, DelCheck 타입을 제외하고 다운로드 2: Hidden컬럼을 제외하고 다운로드 |
| Merge                | Number  | 선택   | 헤더의 머지의 다운로드 적용 방식 설정 (Default=0)                                                                                                      |
| Multipart            | Boolean | 선택   | 다운로드 받을 데이터 전달 방식 (Default=1)                                                                                                          |
| NumberFormatMode     | Number  | 선택   | 실수 형태의 데이터 타입에 대한 셀서식 설정 방식 설정 (Default=0)                                                                                             |
| NumberTypeToText     | Boolean | 선택   | 숫자타입 셀 데이터를 문자 타입으로 다운로드 받을지 여부. 숫자타입 컬럼의 일부 셀에 포맷을 변경하여 문자열을 삽입하는 경우 사용 Default=0                                                     |
| ReportXMLURL         | String  | 선택   | 엑셀파일에 타이틀이나 패턴등을 별도의 xml파일을 통해 설정                                                                                                      |
| ReqHeader            | Object  | 선택   | Request Header에 값 설정                                                                                                                   |
| SheetDesign          | Number  | 선택   | 디자인 다운로드 적용 여부 Default=0                                                                                                               |
| SheetName            | String  | 선택   | 엑셀WorkSheet이름, Default="Sheet"                                                                                                         |
| TextToGeneral        | Boolean | 선택   | Type:”Text”의 엑셀 서식 형식 Default=1(일반)                                                                                                    |
| TitleAlign           | String  | 선택   | Default="center"(중앙정렬)                                                                                                                 |
| TitleText            | String  | 선택   | Default=""(사용안함)                                                                                                                       |
| URL                  | String  | 선택   | Default=""(사용안함)                                                                                                                       |
| UserMerge            | String  | 선택   | Default=""(사용안함)                                                                                                                       |
| UseXhr               | Boolean | 선택   | xhr 통신을 이용해 엑셀 파일을 다운로드 Default=false                                                                                                  |
| WordWrap             | Boolean | 선택   | Default=1(줄바꿈 허용)                                                                                                                      |

- **Example**

```javascript
// 서버에서 데이터를 직접 준비하여다운로드 한다.
var param = {URL:"/sub/ex/bussDeptList.jsp"
,ExtendParam:"DECNO=3422&PartMngNO=982211"
,FileName:"OrgList.xls"};
mySheet. DirectDown2Excel(param);
//xhr통신
var param = {
URL : "/bus/bussinessList.jsp" //비지니스 로직 페이지
,ExtendParam : "sa_nm=양진열&sa_no=980123"
,FileName : "PersonList.xls"
, UseXhr : true
};
Sheet.DirectDown2Excel(param);
var param = {
URL : "/bus/bussinessList.jsp" //비지니스 로직 페이지
,ExtendParam : "sa_nm=양진열&sa_no=980123"
,FileName : "PersonList.xls"
, ReqHeader: {"IBLeaders":"IBSheet"}
};
Sheet.DirectDown2Excel(param);
```

- **제공 버전**

|  **7.0.0.0**   |                             |
|:--------------:|-----------------------------|
|  **7.0.2.0**   | AllTypeToText 속성 추가     |
| **7.0.13.26**  | NumberFormatMode 속성 추가  |
| **7.0.13.89**  | Mode 속성 추가              |
| **7.0.13.230** | ReqHeader, UseXhr 속성 추가 |