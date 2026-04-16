# Down2Pdf Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > Down2Pdf Method

---

- **기능**

> 조회된 데이터가 있는 경우 IBSheet의 내용을 PDF 파일로 변환하여 다운로드 한다.
>
> 이 메서드의 동작방식은 다음과 같다.
>
> 1\) Down2Pdf()메서드를 호출하면 시트의 내용이 Multipart 형태로 서버의 Down2Pdf.jsp/Down2Pdf.aspx 파일에 전달된다.
>
> 2\) Down2Pdf.jsp/Down2Pdf.aspx 파일에서는 넘어온 내용을 iText_2.1.7 라이브러리를 이용하여 pdf 포멧의 파일로 변경하여 다시 화면쪽으로 다운로드 시킨다.

따라서 이 메서드를 사용하려면 다음과 같은 준비과정이 필요하다.

**\* Java 환경**

> 1\. Down2Pdf.jsp 파일이 서버에 존재하며, ibsheet.cfg 파일에 jsp파일에 대한 경로가 정확하게 기재 되어 있어야 한다.
>
> 2\. 서버에 iText 라이브러리가 올라와 있어야 한다.
>
> 3\. 서버에 한글폰트 지원을 위한 ttf 파일이 있어야 하며 jsp 파일에 폰트 폴더에 대한 경로가 정확하게 기재되어 있어야 한다.
>
> **4. Down2Pdf.jsp 파일을 편집기로 열어, 사용하는 서버의 폰트파일 경로와 Encoding을 설정해 준다.**

**\* .Net 환경**

> 1\. Down2Pdf.aspx 파일이 서버에 존재하며, ibsheet.cfg 파일에 aspx파일에 대한 경로가 정확하게 기재 되어 있어야 한다.
>
> 2\. .Net모듈의 경우 자바 모듈을 통해 html 파일을 pdf 파일로 변환처리 하여 다운로드 하기 때문에 서버에 JVM, iText 라이브러리 및 자바버전 모듈이 모두 올라와 있어야 한다.
>
> 3\. 서버에 한글폰트 지원을 위한 ttf 파일이 있어야 하며 ttf 파일은 자바버전 모듈과 같은 위치에 두고 aspx 파일의 ModulePath 에 해당 위치를 정확히 설정해 준다.
>
> **4. Down2Pdf.aspx 파일을 편집기로 열어, 사용하는 서버에서 임시 html파일, pdf 파일을 생성하기 위한 TempFolder(쓰기 권한이 있어야 한다.)와 ttf/jar파일이 위치한 ModulePath, Encoding을 설정해 준다. 자바 모듈인 ibsheet7-1.1.4.jar 파일은 버전에 따라 파일명이 변경되므로 서버에 적용한 자바모듈 파일명을 ModuleFile 정확히 설정해준다.**
>
> 전달되는 인자의 형식은 JSON 타입으로 설정 하고자 하는 정보를 JSON 형태로 구성하여 전달한다.
>
> **DownCols** 인자는 다운로드 받을 컬럼들을 "\|" 문자로 연이은 문자열이다. SaveName과 컬럼인덱스가 모두 가능하다. 널인 경우 모든 컬럼의 자료를 다운로드 받는다.
>
> 예)
>
> var params = { DownCols:"4\|5\|6\|7\|8\|9\|10"};
>
> mySheet.Down2Pdf(params);
>
> **Dpi** 인자는 PDF 변환시 확대 비율을 설정한다. 50 ~ 32800까지 설정 가능하며 값이 클수록 작게 출력된다.
>
> 예)
>
> var params = { Dpi:1800};
>
> mySheet.Down2Pdf(params);
>
> **ExtendParam** 인자는 서버로 전달해야 하는 내용이 있는 경우 Get방식의 QueryString으로 연결하여 설정하면 URL에 지정한 페이지로 같이 전달 된다.
>
> 예)
>
> param = { ExtendParam:"**sawon_name=shkim&sawon_no=12345**",
>
> URL: "/ibsheet7_down2pdf/fp.jsp"};
>
> mySheet.Down2Pdf(param);
>
> **ExtendParamMethod** 인자는 ExtendParam 의 내용을 GET 또는 POST 로 전달할지를 설정한다.
>
> **FileName** 인자는 PDF 다운로드시의 파일명을 설정한다. 파일 확장자는 반드시 pdf 여야 한다. 확장자를 생략할시 자동으로 .pdf 를 붙여 다운로드 한다.  
> 예)
>
> var params = { FileName:"myPDF.pdf"};
>
> mySheet.Down2Pdf(params);
>
> **FontTo** 인자는 PDF에 사용한 한글 폰트를 설정한다. 시트에 한글을 사용한 경우 PDF 변환 모듈에서 적용 가능한 한글 폰트인 굴림 또는 맑은 고딕중 선택하여 영문으로 설정한다. (Gulim 또는 Gothic)
>
> 예)
>
> var params = { FontTo:" Gulim"};
>
> mySheet.Down2Pdf(params);
>
> **Paper** 인자는 PDF 변환시 용지 방향을 설정한다. 가로 : landscape 세로 : portrait
>
> 예)
>
> var params = { Paper:" landscape"};
>
> mySheet.Down2Pdf(params);
>
> **ReqHeader** Request Header에 사용자가 지정한 헤더 정보를 설정한다.
>
> 이 인자를 설정하게 되면 UseXhr:true한 것과 같은 방식으로 동작한다.
>
> **Title** 인자는 PDF 파일에 출력할 제목을 설정한다.
>
> **TitleStyle** 인자는 PDF 파일에 출력할 제목에 적용할 css style을 설정한다.
>
> 예)
>
> var params = {Title:"IB Sheet PDF 파일", TitleStyle:"color:red;size:12pt;" };
>
> mySheet.Down2Pdf(params);
>
> **URL** 인자는 Down2Pdf 와 더불어 서버에서 처리해야 하는 내용이 있는 경우,(가령 로그를 남긴다거나) 로직을 처리할 URL을 넣어주면 Down2Pdf.jsp 페이지를 호출하기 전에 먼저 URL인자에서 설정한 페이지를 호출한다. 따라서 설정 페이지에서는 작업이 끝난 후, request를 Down2Pdf.jsp 페이지로 전달하여야 한다.
>
> 예)
>
> var param = { [URL:"/ibsheet7_down2pdf/fp.jsp](file:///D:\project\ibsheet7-manual2md\20200206\%22\ibsheet7_down2pdf\fp.jsp)"};
>
> mySheet.Down2Pdf(param);
>
> 서버쪽 페이지)
>
> RequestDispatcher rd= request.getRequestDispatcher("/ibsheet7_down2pdf/ Down2Pdf.jsp");
>
> rd.forward(request,response);
>
> **UseXhr** 인자는 다운로드시 통신 방식을 xhr로 설정하는 인자이다.
>
> 기존 다운로드는 iframe를 통한 form submit 방식으로 동작하였다.
>
> 프레임웍의 각종 보안처리로 인하여 iframe를 사용할 수 없다거나 Cookie(파일 다운로드 완료 후 화면의 대기이미지 닫을 때 필요)를 읽고 쓸수 없을 때 이 속성을 true로 설정하면 된다.
>
> **WordWrap** 인자는 셀 텍스트 줄바꿈 여부를 설정한다.

- **Syntax**

|        |                                    |
|:------:|------------------------------------|
| Syntax | ObjId.**Down2Pdf**([parameters]) |

- **Info**

| Parameter         | Type    | 필수여부 | 설 명                                                                 |
| ----------------- | ------- | ---- | ------------------------------------------------------------------- |
| DownCols          | String  | 선택   | 다운로드 받을 열들을 \| 로 연결. Default=""(모두 받음)                              |
| Dpi               | Integer | 선택   | 축소/확대 비율. 값이 작을 수록 크게 출력된다. 50~32840 사이 값으로 설정 가능하다. Default = 2000 |
| ExtendParam       | String  | 선택   | 서버로 전달해야 하는 내용이 있는 경우 Get 방식의 QueryString으로 연결하여 설정Default=""       |
| ExtendParam       | String  | 선택   | Default=""(사용안함)                                                    |
| ExtendParamMethod | String  | 선택   | Default="GET"                                                       |
| FileName          | String  | 선택   | 저장할 파일 명 Default="IBSheet.pdf"                                      |
| FontTo            | String  | 선택   | Default = "Gothic"                                                  |
| Paper             | String  | 선택   | 용지 방향 설정 landscape 또는 portrait Default = "landscape"                |
| ReqHeader         | Object  | 선택   | Request Header에 값 설정                                                |
| Title             | String  | 선택   | Default = ""                                                        |
| TitleStyle        | String  | 선택   | Default = ""                                                        |
| URL               | String  | 선택   | Default=""(사용안함)                                                    |
| UseXhr            | Boolean | 선택   | xhr 통신을 이용해 pdf 파일을 다운로드 Default=false                              |
| WordWrap          | Boolean | 선택   | Default=0(사용안함)                                                     |

- **Example**

```
// PDF 파일로 내려 받기
mySheet.Down2Pdf();
// 다운로드할 파일명을 text로 정의하여다운로드 받는다.
mySheet.Down2Pdf({FileName:'text' });
// 다운로드할 컬럼을 지정하여 myPDF.pdf로 다운받는다.
mySheet.Down2Pdf({FileName:"myPDF", DownCols:"7|8|9|4|5|6|10"});
```

- **제공 버전**

|  **7.0.0.0**   |                             |
|:--------------:|-----------------------------|
| **7.0.13.230** | ReqHeader, UseXhr 속성 추가 |

> **  **