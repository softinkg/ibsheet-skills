# OnLoadData Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnLoadData Event

---

- **기능**

> 데이터 조회 관련 메소드 및 저장 메소드 호출시 서버로부터 데이터를 받은후 시트로 로드할때 발생한다.
>
> 이 이벤트는 서버로부터 데이터를 받은 후 데이터를 수정 하거나 암호화 모듈과 연동하는 경우에 사용한다.

- **Syntax**

|        |                                              |
|:------:|----------------------------------------------|
| Syntax | **function 오브젝트ID_OnLoadData**(Data) { } |

- **Parameters**

|           |        |                                |
|:---------:|:------:|:------------------------------:|
| Parameter |  Type  |             설 명              |
|   Data    | String | 조회 XML 또는 JSON 문자열/객체 |

- **Example**

```javascript
function mySheet_OnLoadData(data) {
// 복호화 처리
var decrypt_data = fnDecryption(data);
// 복호화된 데이터 리턴
return decrypt_data;
}
```

- **제공 버전**

7.0.0.0