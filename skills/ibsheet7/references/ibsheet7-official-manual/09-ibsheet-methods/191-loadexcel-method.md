# LoadExcel Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > LoadExcel Method

---

- **기능**

> 엑셀로부터 데이터를 읽어 들여 데이터 영역에 표시한다.
>
> 전달되는 인자의 형식은 JSON 타입으로 설정 하고자 하는 정보를 JSON 형태로 구성하여 전달한다.
>
> **Append** 속성을 1로 설정하는 경우 기존 데이터에 현재 엑셀 데이터를 첨부하여 로드 할 수 있다.
>
> **ColumnMapping** 속성은 엑셀의 특정 컬럼들만 IBSheet의 첫컬럼부터 차례대로 로딩할 때에 사용한다. 기본값은 널. 이 값이 널이 아니면, Mode 가 HeaderMatch 값을 유지하고 있어도 무시되고 이 기능이 우선적으로 처리된다.
>
> **FileExt** 속성은 업로드 가능한 파일 확장자를 지정한다. 확장자는 "."을 제외한 "xls" 등으로 입력해야 하며, 여러 개의 확장자는 "\|"로 구분하여 입력한다.
>
> IE10 이상, 모던 브라우저에서는 기본값이 "xls\|xlsx"로 설정되고 파일 다이알로그 오픈시 해당 확장자 파일만 보여지게 된다.
>
> [IE10 이상, 모던 브라우저 다이얼로그]
>
> 
>
> 단, IE9 이하는 기본값은 ""으로 "xls\|xlsx"로 입력한 것과 동일하다. 해당 속성을 쓰더라도 파일 다이얼로그에서 파일 선택 이후 확장자가 검증된다.
>
> [IE9 이하 브라우저 다이얼로그]
>
> 
>
> **MaxFileSize** 속성은 처리 대상 파일의 사이즈를 제한하고자 할 때 사용한다.
>
> 설정 단위는 MB이며, 설정 하지 않은 경우 파일 사이즈의 제한없이 사용 할 수 있다. 이 속성은 IE 브라우저의 경우 11이상부터 지원 하고, 그외의 브라우저에서는 모두 지원 한다.
>
> **Mode** 속성은 IBSheet 헤더의 타이틀과 엑셀의 헤더 타이틀을 서로 매칭하여 로딩할지의 여부와 엑셀 로딩시 헤더의 포함 유무를 나타낸다.

| Mode 값      | 설명                                                                                                                       |
| ----------- | ------------------------------------------------------------------------------------------------------------------------ |
| HeaderMatch | 엑셀 문서의 컬럼들이 뒤섞여 있더라도 헤더내의 타이틀들을 비교하여 그 순서대로 찾아서 로딩한다. 화면에 보이는 헤더와 엑셀문서의 헤더 갯수가 같아야 한다.                                   |
| NoHeader    | 엑셀 문서 내에 헤더가 없이 첫 행부터 데이터로 구성되어 있으므로 차례대로 로딩한다.                                                                          |
| HeaderSkip  | 엑셀문서의 첫 행부터 그리드의 헤더 행 수 만큼은 헤더데이타 이지만 무시하도록 하고 그 이후의 행부터 데이타로 간주하여 차례대로 로딩한다. IBSheet의 헤더가 두 줄인 경우 엑셀의 세번째 데이터 행부터 로딩한다. |

> **ReqHeade**r Request Header에 사용자가 지정한 헤더 정보를 설정한다.
>
> 이 인자를 설정하게 되면 UseXhr : true한 것과 같은 방식으로 동작한다.
>
> **SkipEmptyRow** 속성은 엑셀 파일의 데이터 중 빈 행을 생략하는 속성이다.
>
> **StartRow** 속성과 **EndRow** 속성은 읽어올 영역의 시작과 마지막 행의 번호를 의미하며, 설정하지 않을 시 기본적으로 엑셀 영역의 처음부터 끝까지 읽어들인다. 엑셀에서 행번호는 1부터 시작한다.
>
> **StartCol** 속성은 읽어올 컬럼의 시작번호를 의미하며, 설정하지 않을 시 기본적으로 엑셀 첫컬럼부터 끝까지 읽어들인다. 엑셀에서 컬럼번호는 1부터 시작한다.
>
> **UseDOM** 속성은 2007 형식(\*.xlsx)에 대한 엑셀파일의 파싱 방법을 설정한다.
>
> true인 경우 엑셀 파일에 DOM 기반 파싱을 수행하며, false인 경우 엑셀 파일 파싱에 SAX방식을 사용 한다.
>
> LoadExcel 호출시 SAX(default)파싱 방식을 사용하여 대용량처리시 메모리를 적게 사용하고 빠른처리가 되지만 엑셀파일의 데이터 파싱중 서식부분에서 오류가 생길 수 있어서 IBSheet에 로드되는 값이 다르게 표현될 수 있다.
>
> 이때 true를 사용하여 로드를 하는 경우 데이터 값을 그대로 표현 가능하며, 2003, 2007 형식의 엑셀간의 호환성에 유리하다.
>
> **UseXhr** 인자는 업로드시 통신 방식을 xhr로 설정하는 인자이다.
>
> 기존 업로드는 iframe를 통한 form submit 방식으로 동작하였다.
>
> 프레임웍의 보안처리로 인하여 iframe를 사용할 수 없을 때 이 속성을
>
> true로 설정하면 된다.
>
> **WorkSheetName** 속성은 읽어올 엑셀파일의 WorkSheet 이름을 선택한다.
>
> 엑셀의 WorkSheet 선택은 WorkSheetName 인자의 값을 우선적으로 읽어들이고, 이를 실패한 경우, WorkSheetNo 인자의 값으로 WorkSheet를 선택한다.
>
> (사용 예)
>
> ColumnMapping:'1\|2\|3' // IBSheet의 첫번째~ 세번째 컬럼을 엑셀의 1번, 2번, 3번 컬럼들의 값을 차례대로 로딩한다.
>
> ColumnMapping:'7\|\|7' // IBSheet의 첫번째와 세번째 컬럼에만 엑셀의 7번째 컬럼의 값으로 로딩한다.

- **Syntax**

|        |                              |
|:------:|------------------------------|
| Syntax | ObjId.**LoadExcel**([Opt]) |

- **Info**

| Parameter     | Type    | 필수여부 | 설 명                                            |
| ------------- | ------- | ---- | ---------------------------------------------- |
| Append        | Boolean | 선택   | 기존 데이터에 추가 여부 Default=0                        |
| ColumnMapping | String  | 선택   | 엑셀 컬럼 번호 Default=""                            |
| EndRow        | String  | 선택   | 엑셀 로딩완료 행번호 Default="0"                        |
| ExtendParam   | String  | 선택   | 서버로 전달할 추가 파라메터들을 a=1&b=2 형태로 넣어준다. Default="" |
| FileExt       | String  | 선택   | 업로드 가능한 파일 확장자 Default=""                      |
| MaxFileSize   | Number  | 선택   | 최대 허용 파일 사이즈 (단위:MB)                           |
| Mode          | String  | 선택   | 로딩 방식 (헤더매칭등) Default="HeaderMatch"            |
| ReqHeader     | Object  | 선택   | Request Header에 값 설정                           |
| SkipEmptyRow  | Boolean | 선택   | 엑셀의 빈 행 제거. Default = “1”                      |
| StartRow      | String  | 선택   | 엑셀 로딩 행번호 Default="1"                          |
| StartCol      | String  | 선택   | 엑셀 로딩 컬럼번호 Default="1"                         |
| UseDOM        | Boolean | 선택   | 엑셀 로딩시 DOM 기반 파싱 수행 여부 Default="0"             |
| UseXhr        | Boolean | 선택   | xhr 통신을 이용해 엑셀 업로드 Default = false             |
| WorkSheetNo   | String  | 선택   | 엑셀WorkSheet번호 Default="1"                      |
| WorkSheetName | String  | 선택   | 엑셀WorkSheet이름 Default=""                       |

- **Example**

```javascript
// 엑셀로 로딩하기
mySheet.LoadExcel();
// 헤더타이틀을 서로 비교하여 동일한 컬럼끼리 로딩을 하되 7행부터 9 행까지만 읽어들인다.
mySheet.LoadExcel({Mode:'HeaderMatch',StartRow:'7',EndRow:'9'});
// IBSheet의 첫번째 컬럼에 엑셀의 5번째 컬럼의 값을 로딩하고, IBSheet 의 5번째 컬럼에 엑셀의 1번째 컬럼의 값을 로딩함.
mySheet.LoadExcel({ColumnMapping:'5|4|3|2|1'});
//xhr 통신
mySheet.LoadExcel({UseXhr:true});
mySheet.LoadExcel({ReqHeader:{ "IBLeaders":"IBSheet"}});
```

- **제공 버전**

|  **7.0.0.0**   |                             |
|:--------------:|-----------------------------|
| **7.0.13.27**  | MaxFileSize 속성 추가       |
| **7.0.13.111** | FileExt 기본값 변경         |
| **7.0.13.114** | SkipEmptyRow 속성 추가      |
| **7.0.13.230** | ReqHeader, UseXhr 속성 추가 |