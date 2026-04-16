# GetSaveData Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetSaveData Method

---

- **기능**

> 저장 페이지를 호출하여 저장 처리를 완료한 후 생성된 결과를 문자열로 반환한다.
>
> 이 함수는 DoAllSave 또는 DoSave 함수와 달리 저장할 QueryString을 인자로 받아서 저장처리를 하며, 저장결과에 대한 처리 없이 데이터 자체로 반환한다. 이 함수를 통해서 반환된 저장 데이터는 LoadSaveData 함수의 인자로 사용하면 저장 결과를 IBSheet 내부에 표현할 수 있다.
>
> SaveString 에 대한 인코딩이 필요할 경우 함수 호출전에 처리를 해야 한다.

- **Syntax**

|        |                                                                    |
|:------:|--------------------------------------------------------------------|
| Syntax | ObjId.**GetSaveData**(PageUrl, [SaveString], [Param], [Opt]) |

- **Info**

> **Return**: String, 저장 데이터의 문자열

| Parameter     | Type   | 필수여부 | 설 명                            |
| ------------- | ------ | ---- | ------------------------------ |
| PageUrl       | String | 필수   | 저장 처리할 페이지 URL                 |
| SaveString    | String | 선택   | 저장할 Query String, Default=""   |
| Param         | String | 선택   | 저장 조건 Query String, Default="" |
| Opt.ReqHeader | Object | 선택   | 요청헤더 설정 값 객체, Default={}       |

- **Example**

```javascript
//저장 String 가져오기 – 트랜잭션이 발생한 것만 저장할 경우
var SaveStr = mySheet.GetSaveString();
//저장할 내역이 없거나 저장 validation에서 오류가 발생한 경우
if (SaveStr == "" || SaveStr == "KeyFieldError") return;
//저장 처리 결과 읽어오기
var rtnData = mySheet.GetSaveData("save.jsp", SaveStr);

//돌아온 결과를 시트에 반영
mySheet.LoadSaveData(rtnData);
```

- **제공 버전**

|  **7.0.0.0**   |                      |
|:--------------:|----------------------|
| **7.0.13.166** | Param JSON 구조 추가 |