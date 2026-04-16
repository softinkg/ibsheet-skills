# GetSearchData Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetSearchData Method

---

- **기능**

> 조회 페이지를 호출하여 조회 처리를 완료한 후 생성된 조회결과 데이터를 문자열로 반환한다. 이 함수는 DoSearch 함수와 달리 조회결과에 대한 처리 없이 조회 데이터 자체를 반환한다. 이 함수를 통해서 반환된 조회 데이터는 LoadSearchData 함수의 인자로 사용하면 조회 결과를 IBSheet 내부에 표현할 수 있다.

- **Syntax**

|        |                                                      |
|:------:|------------------------------------------------------|
| Syntax | ObjId.**GetSearchData**(PageUrl, [Param], [Opt]) |

- **Info**

> **Return**: String, 조회 데이터의 문자열

| Parameter     | Type   | 필수여부 | 설 명                            |
| ------------- | ------ | ---- | ------------------------------ |
| PageUrl       | String | 필수   | 조회 처리할 페이지 URL                 |
| Param         | String | 선택   | 조회 조건 Query String, Default="" |
| Opt.ReqHeader | Object | 선택   | 요청헤더 설정 값 객체, Default={}       |

- **Example**

```javascript
//조회 데이터 읽어오기
var sXml = mySheet.GetSearchData("list.jsp");
//조회 결과 내용을 표현하기
mySheet.LoadSearchData(sXml);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **