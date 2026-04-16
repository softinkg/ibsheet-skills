# GetSaveString Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetSaveString Method

---

- **기능**

> 저장 시 사용되는 데이터의 Query String을 문자열로 반환한다.
>
> 이 함수는 보안 모듈을 사용하여 저장하는 경우 저장할 문자열을 반환하여 보안모듈에서 암호화 하여 저장 처리할 수 있도록 한다.
>
> 이 함수를 호출하면 저장 String을 생성하며 필수 입력 항목을 확인하고, OnValidation 이벤트가 발생하여 사용자 Validation 로직도 처리한다.
>
> AllSave인자는 1일때 DoAllSave 함수를 호출할 때 사용되는 저장String과 동일하며, 0 일때 DoSave함수를 호출할 때 사용되는 저장String과 동일하다.
>
> UrlEncode는 1일 때 Query String의 한글 문자를 모두 Encoding한다.
>
> Col 인자는 AllSave인자가 0일 때 사용하며 저장 대상이 되는 컬럼을 설정한다.
>
> Mode인자는 Query String 문자열 조합방법을 설정한다.
>
> 설정값에 따른 Query String 결과는 다음과 같다.
>
> Validation 체크 결과가 실패인 경우 기본으로 **KeyFieldError** 문자열이 반환되고, ibmsg의 SYS_InvalidGetSaveString에 값이 설정되어 있는 경우 해당 값으로 반환된다.

| Mode | 설명                              | 예                        |
| ---- | ------------------------------- | ------------------------ |
| 1    | 셀기준 조합 (SaveName 기준 Array 형식)   | sSeq=1&sStatus=R..       |
| 2    | 컬럼기준 조합 (SaveName 기준 구분자 조합 형식) | sSeq=1\|2&sStatus=R\|U.. |

> "선택" 인자는 json 형식으로 속성 설정이 가능하다.(Example 참고)

- **Syntax**

|        |                                  |
|:------:|:---------------------------------|
| Syntax | ObjId.**GetSaveString**([Opt]) |

- **Info**

> **Return**: String, 저장할 Query String

| Parameter             | Type          | 필수여부 | 설 명                                                                |
| --------------------- | ------------- | ---- | ------------------------------------------------------------------ |
| Opt.AllSave           | Boolean       | 선택   | 전체 저장 여부 (Default=0)                                               |
| Opt.UrlEncode         | Boolean       | 선택   | UrlEncode 여부 (Default=1)                                           |
| Opt.Col               | Long / String | 선택   | 대상이 되는 기준 컬럼 또는 SaveName (Default =상태 컬럼)                          |
| Opt.Prefix            | String        | 선택   | 저장시 SaveName 앞에 붙이고자 하는 문자열 (Default="")                           |
| Opt.Mode              | Integer       | 선택   | Query String 문자열 조합방법을 설정Mode=1, Mode=2 (Default =1)               |
| Opt.Delim             | String        | 선택   | Mode=2일때, 연결될 구분자 설정 (Default ="\|")                               |
| Opt.StdColValue       | String        | 선택   | 기준컬럼의 추출 대상 값을 구분자 '\|' 로 연결한 문자열                                  |
| Opt.ValidKeyField     | Boolean       | 선택   | KeyField 체크 여부 (Default=1)                                         |
| Opt.ValidFullInput    | Boolean       | 선택   | FullInput 체크 여부 (Default=1)                                        |
| Opt.ValidEditLen      | Boolean       | 선택   | 저장시 EditLen 속성을 통한 길이 체크 여부                                        |
| Opt.NoSelectCellEvent | Boolean       | 선택   | KeyField 체크로 인해 포커스 이동시 OnSelectCell 이벤트 발생여부 (Default=0 : 이벤트 발생) |

- **Example**

```javascript
//DoAllSave 함수 사용과 동일한 저장 String 가져오기
var SaveStr = mySheet.GetSaveString({"AllSave":1});
//DoSave 함수 사용과 동일한 저장 String 가져오기
//– 트랜잭션이 발생한 것만 저장할 경우
var SaveStr = mySheet.GetSaveString();
//DoSave 함수 사용과 동일한 저장 String 가져오기
//– 체크박스 컬럼타입의 Check된 것만 저장하는 경우
// (해당 컬럼의 Index가 4일 때)
var SaveStr = mySheet.GetSaveString({"Col":4});
//DoSave 함수 사용과 동일한 저장 String 가져오기
// 돌아오는 값은 pre_AA=1&pre_BB=2&pre_CC=3 형태가 된다.
var SaveStr = mySheet.GetSaveString({"Prefix":"pre_"});
```

- **see also**

> **[GetSaveJson](#getsavejson-method) Method**

- **제공 버전**

| **7.0.0.0**    |                                                                          |
| -------------- | ------------------------------------------------------------------------ |
| **7.0.12.4**   | 인자구조 변경, ValidKeyField, ValidFullInput 인자 속성 추가 (이전 방식의 인자구조는 이전 가이드 참고) |
| **7.0.13.27**  | StdColValue 속성 추가                                                        |
| **7.0.13.200** | NoSelectCellEvent 속성 추가                                                  |