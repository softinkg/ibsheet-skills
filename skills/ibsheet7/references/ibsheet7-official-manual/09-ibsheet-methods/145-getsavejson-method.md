# GetSaveJson Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetSaveJson Method

---

- **기능**

> 저장 대상의 데이터를 Json 객체로 반환한다.
>
> 이 함수를 호출하면 저장 객체를 생성하며 필수 입력 항목을 확인하고, OnValidation 이벤트가 발생하여 사용자 Validation 로직도 처리한다.
>
> Col 인자는 AllSave인자가 0일 때 사용하며 저장 대상이 되는 컬럼을 설정한다. 2개행 이상의 단위데이터행 구조인 경우 Col 인자에 Index를 설정할 경우 Json 객체 생성시 각각의 행 단위로 생성되고, SaveName으로 설정할 경우 단위데이터행 단위로 생성 한다.
>
> Validation 체크 결과가 실패인 경우 결과 코드와 메시지가 반환된다.

- 처리대상 행이 없는 경우

> **Code : "IBS000", Message : "NoTargetRows"**

- 필수입력 누락인 경우

> **Code : "IBS010", Message : "KeyFieldError"**

- Validation 오류인 경우

> **Code : "IBS020", Message : "InvalidInputError"**

- **Syntax**

|        |                                   |
|:------:|-----------------------------------|
| Syntax | ObjId.**GetSaveJson**([Option]) |

- **Info**

> **Return**: Object, 저장할 데이터의 Json 객체

| Parameter            | Type            | 필수여부 | 설 명                                               |
| -------------------- | --------------- | ---- | ------------------------------------------------- |
| Option.AllSave       | Boolean         | 선택   | 전체 저장 여부, (Default =0)                            |
| Option.AllTypeToText | Boolean         | 선택   | Json객체의 모든 데이터를 문자열로 반환한다 (Default =0)            |
| Option.StdCol        | Number / String | 선택   | 대상이 되는 기준 컬럼의 Index 또는 SaveName, (Default =상태 컬럼) |
| Opt.StdColValue      | String          | 선택   | 기준컬럼의 추출 대상 값을 구분자 '\|' 로 연결한 문자열                 |
| Opt.ValidKeyField    | Boolean         | 선택   | KeyField 체크 여부 (Default=1)                        |
| Opt.ValidFullInput   | Boolean         | 선택   | FullInput 체크 여부 (Default=1)                       |
| Opt.ValidEditLen     | Boolean         | 선택   | 저장시 EditLen 속성을 통한 길이 체크 여부                       |

- **Example**

```javascript
//모든 행의 데이터를 객체로 받기
var SaveJson = mySheet.GetSaveJson({AllSave:1});
//저장 대상의 데이터를 객체로 받기 (트랜잭션이 발생한 행)
var SaveJson = mySheet.GetSaveJson();
// 4번째 컬럼이 Check된 행의 데이터를 객체로 받기
var SaveJson = mySheet.GetSaveJson({StdCol:4});
```

- **제공 버전**

|  **7.0.0.0**  |                         |
|:-------------:|-------------------------|
| **7.0.13.27** | StdColValue 속성 추가   |
| **7.0.13.97** | AllTypeToText 속성 추가 |