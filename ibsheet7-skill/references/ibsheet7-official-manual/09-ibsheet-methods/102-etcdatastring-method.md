# EtcDataString Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > EtcDataString Method

---

- **기능**

> EtcData 객체에 설정된 키와 값을 모두 조합하여 "키이름1=키값1&키이름2=키값2"와 같은 QueryString 형태로 반환 한다.

- **Syntax**

|        |                                        |
|:------:|----------------------------------------|
| Syntax | ObjId.**EtcDataString**([UrlEncode]) |

- **Info**

> **Return**: String, EtcData에 설정된 키와 값에 대한 QueryString 문자열

| Parameter | Type    | 필수여부 | 설 명                     |     |
| --------- | ------- | ---- | ----------------------- | --- |
| UrlEncode | Boolean | 선택   | 인코딩 처리 여부 (Default = 0) |     |

- **Example**

```javascript
// EtcData 영역의 값을 문자열로 받는다.
var param = mySheet.EtcDataString();
//저장시 인자로 넘긴다.
mySheet.DoSave("Save.jsp", Param);
```

- **제공 버전**

> **7.0.0.0**