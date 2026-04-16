# Down2Text Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > Down2Text Method

---

- **기능**

> 조회된 데이터가 있는 경우 IBSheet의 내용을 텍스트 파일로 변환하여 다운로드 한다.
>
> 전달되는 인자의 형식은 JSON 타입으로 설정 하고자 하는 정보를 JSON 형태로 구성하여 전달한다.
>
> **DownCols** 인자는 다운로드 받을 컬럼들을 "\|" 문자로 연이은 문자열이다. SaveName과 컬럼인덱스가 모두 가능하다. 널인 경우 모든 컬럼의 자료를 다운로드 받는다.
>
> **DownCombo** 인자는 콤보와 콤보에디트의 선택항목을 TEXT 형태와 CODE 형태로 다운로드 받을 수 있다. 기본값은 "TEXT" 이며 "CODE"를 입력하면 TEXT 대신 해당 CODE 로 다운로드 받는다.
>
> **DownHeader** 인자는 헤더를 포함하여 다운로드 받을지 설정한다. 기본값은 1(헤더 포함) 이다.  
>   
> **DownRows** 인자는 다운로드 받을 행들을 "\|" 문자로 연이은 문자열이다. 널인 경우 모든 행의 자료를 다운로드 받는다.
>
> **DownSum** 인자는 합계를 포함하여 다운로드 받을지 설정한다. 기본값은 1(합계 포함) 이다.
>
> **DownTreeHide** 인자는 트리의 접혀진 행을 다운 받을 때 사용한다.
>
> **ExtendParam** 인자는 서버로 전달해야 하는 내용이 있는 경우 Get 방식의 QueryString으로 연결하여 설정하면 URL에 지정한 페이지로 같이 전달 된다.
>
> 예제)
>
> param = {**ExtendParam**:"**sawon_name=shkim&sawon_no=12345**",
>
> URL:"/ibsheet7_down2text_extendparam/fp.jsp };
>
> **ExtendParamMethod** 인자는 ExtendParam 의 내용을 GET 또는 POST 로 전달할지를 설정한다.  
>   
> **FileName** 인자는 텍스트 다운로드시의 파일명을 설정한다. 파일 확장자는 반드시 txt 여야 한다. 확장자를 생략할시 자동으로 .txt 를 붙여 다운로드 한다  
> 예)
>
> var params = { FileName : "myFile.txt "};
>
> mySheet.Down2Text(params);
>
> **ReqHeader** Request Header에 사용자가 지정한 헤더 정보를 설정한다.
>
> 이 인자를 설정하게 되면 UseXhr : true한 것과 같은 방식으로 동작한다.
>
> **UseXhr** 인자는 다운로드시 통신 방식을 xhr로 설정하는 인자이다.
>
> 기존 다운로드는 iframe를 통한 form submit 방식으로 동작하였다.
>
> 프레임웍의 각종 보안처리로 인하여 iframe를 사용할 수 없다거나 Cookie(파일 다운로드 완료 후 화면의 대기이미지 닫을 때 필요)를 읽고 쓸수 없을 때 이 속성을 true로 설정하면 된다.

- **Syntax**

|        |                                     |
|:------:|-------------------------------------|
| Syntax | ObjId.**Down2Text**([parameters]) |

- **Info**

| Parameter         | Type    | 필수여부 | 설 명                                                           |
| ----------------- | ------- | ---- | ------------------------------------------------------------- |
| ColDelim          | String  | 선택   | 셀 자료 사이에 표시될 컬럼 구분자 Default=" " (공백 형식)                       |
| DownCols          | String  | 선택   | 다운로드 받을 열들을 \| 로 연결. Default=""(모두 받음)                        |
| DownCombo         | String  | 선택   | 콤보의 TEXT / CODE 형태의 다운로드 여부 Default="TEXT"                    |
| DownHeader        | Boolean | 선택   | 헤더의 다운로드 여부 Default=1                                         |
| DownSum           | Boolean | 선택   | 합계의 다운로드 여부 Default=1                                         |
| DownRows          | String  | 선택   | 다운로드 받을 행들을 \| 로 연결. Default=""(모두 받음)                        |
| DownTreeHide      | Boolean | 선택   | 트리의 접혀진 행 다운 여부 Default=0(다운 안받음)                             |
| ExtendParam       | String  | 선택   | 서버로 전달해야 하는 내용이 있는 경우 Get 방식의 QueryString으로 연결하여 설정Default="" |
| ExtendParamMethod | String  | 선택   | Default="GET"                                                 |
| FileName          | String  | 선택   | 저장할 파일 명 Default="Test.txt"                                   |
| ReqHeader         | Object  | 선택   | Request Header에 값 설정                                          |
| RowDelim          | String  | 선택   | 행 자료 사이에 표시될 레코드 구분자 Default="\n" (엔터 형식)                     |
| UseXhr            | Boolean | 선택   | xhr 통신을 이용해 엑셀 파일을 다운로드 Default=false                         |

- **Example**

```javascript
// 텍스트 파일로 내려 받기
mySheet.Down2Text();
// 다운로드할 파일명을 text로 정의하여다운로드 받는다.
mySheet.Down2Text({FileName:'text' });
// 콤보는 코드로 받고, 헤더와 합계는 제외하고 컬럼은 왼쪽에서 3개의 컬럼만 다운로드 한다.
mySheet.Down2Text({DownCombo:'CODE', DownRows:'', DownCols:'0|1|2', DownHeader:0, DownSum:0});
//CSV 파일로 내려 받기.
mySheet.Down2Text({FileName:'myfile.csv', ColDelim:","});
//xhr 통신
// 다운로드할 파일명을 text로 정의하여다운로드 받는다.
mySheet.Down2Text({FileName:'text', ReqHeader:{ "IBLeaders":"IBSheet"} });
mySheet.Down2Text({FileName:'text', UseXhr:true });
```

- **제공 버전**

|  **7.0.0.0**   |                             |
|:--------------:|-----------------------------|
| **7.0.13.230** | ReqHeader, UseXhr 속성 추가 |

> **  **