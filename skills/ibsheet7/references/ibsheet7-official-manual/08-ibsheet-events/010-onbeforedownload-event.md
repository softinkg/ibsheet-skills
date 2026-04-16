# OnBeforeDownload Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnBeforeDownload Event

---

- **기능**

> 엑셀, 텍스트, Pdf 다운전에 데이터가 만들어지고 폼이 서브밋되기 전에 발생한다. 해당 이벤트 안에서 폼을 서브밋해야 정상적으로 다운이 된다.

- **Syntax**

|        |                                                                 |
|:------:|-----------------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnBeforeDownload**(downloadType, frm) { } |

- **Parameters**

| Parameter    | Type   | 설 명                                                           |
| ------------ | ------ | ------------------------------------------------------------- |
| downloadType | String | 다운로드 종류. "EXCEL" : 엑셀 다운로드 "TEXT" : 텍스트 다운로드 "PDF" : PDF 다운로드 |
| frm          | Object | Html Form 객체                                                  |

- **Example**

```javascript
function mySheet_OnBeforeDownload(type, frm) {
//서버측으로 전달될 문자열을 확인
var data = frm.Data.value;
//다운로드 폼을 서브밋
frm.submit();
}
```

- **제공 버전**

| **7.0.13.43** |     |
|---------------|-----|