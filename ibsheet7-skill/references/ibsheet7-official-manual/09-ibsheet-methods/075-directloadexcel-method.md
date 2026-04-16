# DirectLoadExcel Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DirectLoadExcel Method

---

- **기능**

> LoadExcel 처럼 엑셀 문서를 읽어들이는 것은 동일하지만, 엑셀 문서의 내용을 IBSheet 에 담지 않고 서버쪽에서 지정한 페이지로 전달한다.
>
> 따라서 엑셀로부터 넘어온 데이터를 받아 줄 페이지를 별도로 개발하여야 하고, DirectLoadExcel의 ExtendParam 을 통해 엑셀의 내용을 받아 줄 포워딩 페이지(**FP=/jsp/excelsave.jsp**) 경로를 넣어주면 된다.
>
> 포워딩 페이지에서 엑셀의 내용을 받는 방법은 request 객체 안에 "SHEETDATA"라는 이름으로 값을 뽑아 낼수 있다. SHEETDATA안의 내용은 List( Map)으로 구성되어있고, Map의 키는 IBSheet 각 컬럼의 SaveName이 된다.
>
> Ex) //포워딩 페이지..
>
> List sheet = (List)request.getAttribute("SHEETDATA");
>
> for(int i=0;i<sheet.size();i++){
>
> Map mp =(Map)sheet.get(i);
>
> }
>
> 또한 화면으로부터 ExtendParam으로 전달했던 내용들은 포워딩 페이지에서 모두 getAttribute로 얻을 수 있다.
>
> 각 인자의 자세한 설명은 LoadExcel 함수를 참고 한다.
>
> p.s : ibsheet.cfg 안에서 DirectLoadExcel 경로를 설정해야 바르게 동작한다.

- **Syntax**

|        |                                           |
|:------:|-------------------------------------------|
| Syntax | ObjId.**DirectLoadExcel**([parameters]) |

- **Info**

| Parameter     | Type    | 필수여부 | 설 명                                                 |
| ------------- | ------- | ---- | --------------------------------------------------- |
| ColumnMapping | String  | 선택   | 엑셀 컬럼 번호 Default=""                                 |
| EndRow        | String  | 선택   | 엑셀 로딩완료 행번호 Default="0"                             |
| ExtendParam   | String  | 필수   | 서버로 전달될 파라미터를 쿼리스트링 형태로 넣음. **특히 저장작업을 수행할 FP는 필수** |
| FileExt       | String  | 선택   | 업로드 가능한 파일 확장자 Default=""                           |
| MaxFileSize   | Number  | 선택   | 파일의 사이즈 제한시 사용 설정단위 MB                              |
| Mode          | String  | 선택   | 로딩 방식 (헤더매칭등) Default="HeaderMatch"                 |
| ReqHeader     | Object  | 선택   | Request Header에 값 설정                                |
| SkipEmptyRow  | Boolean | 선택   | 엑셀의 빈 행 제거. Default = “1”                           |
| StartRow      | String  | 선택   | 엑셀 로딩 행번호 Default="1"                               |
| UseXhr        | Boolean | 선택   | xhr 통신을 이용해 엑셀 파일을 업로드 Default=false                |
| WorkSheetNo   | String  | 선택   | 엑셀WorkSheet번호, Default="1"                          |
| WorkSheetName | String  | 선택   | 엑셀WorkSheet이름 Default=""                            |

- **Example**

```javascript
// 참고 함수
function makeExParam(key,data){
return "&"+encodeURIComponent(key)+"="+encodeURIComponent(data);
}
// 엑셀로 넘어온 내용을 전달할 포워딩 페이지(ContextRoot명은 빼고 적는다.)
var param =makeExParam( "FP" ,"/bu/MassSave.jsp");
param += makeExParam("sname","chris");
param += makeExParam("date","20091221");
var parameters = { Mode : mch, StartRow: "1", ExtendParam:param}
// 엑셀로 로딩하여 서버에서 즉시 처리하기
mySheet. DirectLoadExcel(parameters);
// MassSave.jsp 페이지 내용
// 1. 엑셀의 내용을 찍어본다. (데이터확인)
String PRINT_STR = "";
ArrayList keys = new ArrayList();
List li = (List)request.getAttribute("SHEETDATA");
for(int i=0;i<li.size();i++){
Map mp = (Map)li.get(i);
// 헤더 한줄만 뿌려주자.
If(i==0){
Iterator it = mp.keySet().iterator();
while(it.hasNext()){
String key = (String)it.next();
PRINT_STR += key+"\t";
keys.add(key);
}
PRINT_STR += "\\n";
}
// 데이터를 뿌리자
for(int c=0;c<keys.size();c++){
PRINT_STR += mp.get(keys.get(c))+"\t";
}
PRINT_STR += "\\n";
}
// 서버 콘솔에서 확인
System.out.println(PRINT_STR);
// 2. ExtendParam으로 넘긴 내용도 확인해 본다.
System.out.println( request.getAttribute("sname"));
System.out.println( request.getAttribute("date"));
// 3. 최종적으로 화면에 결과를 리턴한다.
Out.println("<script>alert(‘총 데이터 건수 :"+li.size()+" 건이\n저장 되었습니다.');</script>");
```

- **제공 버전**

|  **7.0.0.0**   |                             |
|:--------------:|-----------------------------|
| **7.0.13.27**  | MaxFileSize 속성 추가       |
| **7.0.13.114** | SkipEmptyRow 속성 추가.     |
| **7.0.13.230** | ReqHeader, UseXhr 속성 추가 |