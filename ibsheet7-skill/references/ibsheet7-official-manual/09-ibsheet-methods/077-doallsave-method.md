# DoAllSave Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DoAllSave Method

---

- **기능**

> 데이터의 트랜잭션 상태에 관계 없이 모든 데이터를 저장 하도록 페이지를 호출한다.
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

> "선택" 인자는 json 형식으로 속성 설정이 가능하다.(Example 참고).

- **Syntax**

|        |                                   |
|:------:|:----------------------------------|
| Syntax | ObjId.**DoAllSave**(Url, [Opt]) |

- **Info**

> **Return**: Boolean, 저장 처리여부

| Parameter          | Type     | 필수여부 | 설 명                                                  |
| ------------------ | -------- | ---- | ---------------------------------------------------- |
| Url                | String   | 필수   | 저장 처리할 페이지 파일 이름                                     |
| Opt.CallBack       | Function | 선택   | 조회 후 사용자 정의 콜백함수                                     |
| Opt.Param          | String   | 선택   | 저장을 위한 Parameter (Default="")                        |
| Opt.UrlEncode      | Boolean  | 선택   | IBSheet 위의 데이터를 인코딩할지 여부를 설정 (Default=1)             |
| Opt.Mode           | Number   | 선택   | Query String 문자열 조합방법을 설정Mode=1, Mode=2 (Default =1) |
| Opt.Delim          | String   | 선택   | Mode=2일때, 연결될 구분자 설정 (Default ="\|")                 |
| Opt.ReqHeader      | Object   | 선택   | 요청헤더 설정 값 객체, (Default={})                           |
| Opt.ValidKeyField  | Boolean  | 선택   | KeyField 체크 여부 (Default=1)                           |
| Opt.ValidFullInput | Boolean  | 선택   | FullInput 체크 여부 (Default=1)                          |
| Opt.ValidEditLen   | Boolean  | 선택   | 저장시 EditLen 속성을 통한 길이 체크 여부                          |

- **Example**

```javascript
// 모든 내역 저장하기
var Result = mySheet.DoAllSave("save.jsp", { Param : "id=khlee&seq=1" });
//저장 실패한 경우 에러 메시지를 표시하고, 성공한 경우 조회처리
if(!Result){
alert("저장 실패했습니다. 다시 시도하세요");
} else {
mySheet.DoSearch("list.jsp");
}
//설정할 "선택" 인자 json형식으로 속성 설정하기
mySheet.DoAllSave(PageUrl, { UrlEncode:0, Mode:2, Delim:"$"});
// 파라미터 JSON 구조로 설정
mySheet.DoAllSave(PageUrl,
{ ReqHeader: {"Content-Type":"application/json"}
});
```

- **제공 버전**

|  **7.0.0.0**   |                                              |
|:--------------:|----------------------------------------------|
|  **7.0.1.0**   | 저장 처리 여부에 따른 리턴값 추가            |
|  **7.0.12.4**  | ValidKeyField, ValidFullInput 인자 속성 추가 |
| **7.0.13.166** | Param JSON 구조 추가                         |

> **  **