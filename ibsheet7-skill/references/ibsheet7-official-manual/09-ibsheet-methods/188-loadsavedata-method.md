# LoadSaveData Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > LoadSaveData Method

---

- **기능**

> 저장 데이터를 함수의 인자로 전달 받아 결과를 IBSheet 내부에 처리한다.
>
> 이 함수는 보안 모듈이 사용 될 경우 복호화된 저장 데이터을 읽어 들이기 위한 것이다. 저장 데이터는 GetSaveData 함수를 통해 읽어 들일 수 있고, 이 함수에 인자로 설정하면 처리 결과를 표현하고, OnSaveEnd 이벤트를 발생한다.

- **Syntax**

|        |                                          |
|:------:|------------------------------------------|
| Syntax | ObjId.**LoadSaveData**(Content, [Opt]) |

- **Info**

> **Return**: None.

| Parameter    | Type     | 필수여부 | 설 명                      |
| ------------ | -------- | ---- | ------------------------ |
| Content      | String   | 필수   | 저장XML 또는 저장JSON 문자열      |
| Opt.CallBack | Function | 선택   | CallBack 함수              |
| Opt.Event    | Boolean  | 선택   | 완료 이벤트 발생 여부 Default = 1 |

- **Example**

```javascript
//저장 작업 Ajax 처리
var rtnData = mySheet.GetSaveData("Action.do",param);
//저장 결과 표현하기
mySheet.LoadSaveData(rtnData);
```

- **제공 버전**

|  **7.0.0.0**  |                           |
|:-------------:|---------------------------|
| **7.0.13.43** | CallBack, Event 속성 추가 |