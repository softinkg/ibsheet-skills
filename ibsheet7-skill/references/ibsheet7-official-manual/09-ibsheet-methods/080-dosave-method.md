# DoSave Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DoSave Method

---

- **기능**

> 데이터의 트랜잭션 상태 또는 특정 컬럼 데이터에 따라 저장 처리한다.
>
> Col 인자에 아무것도 설정하지 않는 경우 트랜잭션 상태가 조회가 아닌 데이터 행만 저장 처리하고, Col에 특정 인자가 있는 경우 해당 컬럼에 값이 있는 데이터만 저장 처리한다.
>
> 해당 컬럼이 CheckBox 형태 인 경우 CheckBox에 체크된 것만 저장 처리한다.
>
> 데이터 건수가 한건도 없으면 경고 메시지를 표시하고, 처리는 중단한다.
>
> 저장 준비를 위한 저장 데이터를 모으는 과정에서 OnValidataion 이벤트가 발생하며 사용자 정의 로직에 따라 OnValidataion에서 실패한 경우 저장 처리는 중단한다.
>
> Url로 저장 페이지를 호출하고 저장 처리를 완료하여 저장 XML을 읽어 들이고 난 후 OnSaveEnd 이벤트를 발생하고 처리는 종료된다.
>
> Mode인자는 Query String 문자열 조합방법을 설정한다.
>
> 설정값에 따른 Query String 결과는 다음과 같다.

| Mode | 설명                              | 예                        |
| ---- | ------------------------------- | ------------------------ |
| 1    | 셀기준 조합 (SaveName 기준 Array 형식)   | sSeq=1&sStatus=R..       |
| 2    | 컬럼기준 조합 (SaveName 기준 구분자 조합 형식) | sSeq=1\|2&sStatus=R\|U.. |

> "선택" 인자는 json 형식으로 속성 설정이 가능하다.(Example 참고)

- **Syntax**

|        |                                |
|:------:|:-------------------------------|
| Syntax | ObjId.**DoSave**(Url, [Opt]) |

- **Info**

> **Return**: Boolean, 저장 처리여부

| Parameter          | Type            | 필수여부 | 설 명                                                 |
| ------------------ | --------------- | ---- | --------------------------------------------------- |
| Url                | String          | 필수   | 저장 처리할 페이지 파일 이름                                    |
| Opt.Param          | String          | 선택   | 저장을 위한 Parameter (Default="")                       |
| Opt.CallBack       | Function        | 선택   | 조회 후 사용자 정의 콜백함수                                    |
| Opt.Col            | Number / String | 선택   | 저장 대상이 되는 기준 컬럼의 Index 또는 SaveName Default=상태컬럼(-1) |
| Opt.Quest          | Boolean         | 선택   | 저장 시 확인 메시지 표시 여부 설정, Default=1                     |
| Opt.UrlEncode      | Boolean         | 선택   | IBSheet 위의 데이터를 인코딩할지 여부를 설정, Default=1             |
| Opt.Mode           | Integer         | 선택   | Query String 문자열 조합방법을 설정Mode=1, Mode=2 (Default=1) |
| Opt.Delim          | String          | 선택   | Mode=2일때, 연결될 구분자 설정 (Default="\|")                 |
| Opt.ReqHeader      | Object          | 선택   | 요청헤더 설정 값 객체, (Default={})                          |
| Opt.ValidKeyField  | Boolean         | 선택   | KeyField 체크 여부 (Default=1)                          |
| Opt.ValidFullInput | Boolean         | 선택   | FullInput 체크 여부 (Default=1)                         |
| Opt.ValidEditLen   | Boolean         | 선택   | 저장시 EditLen 속성을 통한 길이 체크 여부                         |

- **Example**

```
//트랜잭션이 일어난 데이터만 저장하기
mySheet.DoSave("Save.jsp" ,{ Param : "id=khlee&seq=1" });
//2컬럼의 CheckBox가 체크된것만 저장하기
mySheet.DoSave("Save.jsp" ,{ Param : "id=khlee&seq=1", Col : 2 });
//설정할 "선택" 인자 json형식으로 속성 설정하기
mySheet.DoSave(PageUrl, { UrlEncode:0, Mode:2, Delim:"$" });
// 파라미터 JSON 구조로 설정
mySheet.DoSave(PageUrl, { ReqHeader: {"Content-Type":"application/json"} });
```

- **제공 버전**

|  **7.0.0.0**   |                                              |
|:--------------:|----------------------------------------------|
|  **7.0.1.0**   | 저장 처리 여부에 따른 리턴값 추가            |
|  **7.0.12.4**  | ValidKeyField, ValidFullInput 인자 속성 추가 |
| **7.0.13.166** | Param JSON 구조 추가                         |

> **  **