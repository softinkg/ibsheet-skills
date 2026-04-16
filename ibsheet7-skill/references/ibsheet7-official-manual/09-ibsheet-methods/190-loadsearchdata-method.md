# LoadSearchData Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > LoadSearchData Method

---

- **기능**

> 조회 데이터(xml or json)를 함수의 인자로 전달 받아 아이비시트에 로딩한다.
>
> 조회 데이터는 GetSearchData 함수나 혹은 별도의 ajax 모듈을 통해 서버로부터 가져올 수 있고, 가져온 데이터 문자열을 이 함수의 인자로 설정하면 조회 데이터를 아이비시트에 로딩하고, OnSearchEnd 이벤트를 발생한다.
>
> 기본적으로 이 함수가 호출되면 기존 데이터는 지워지고 Content데이터가 로딩된다.
>
> 하지만 Append 인자를 사용하는 경우, 기존데이터를 맨 아래 행에 Content데이터를 붙여넣는다.
>
> AppendRow 인자는 Append값이 true 인 경우, Content데이터를 붙여넣을 행을 지정할 수 있다.  
> Fx 인자는 컬럼의 타입에 따라 사용할 수 있는 포멧 유형을 제한하고 대신 조회속도를 향상 시킨다. Fx에서 사용할 수 있는 포멧 형식에 관한 자세한 내용은 이 메뉴얼 마지막 장 Appendix 부분에 설명되어 있다.

- **Syntax**

|        |                                            |
|:------:|--------------------------------------------|
| Syntax | ObjId.**LoadSearchData**(Content, [Opt]) |

- **Info**

> **Return**: None.

| Parameter     | Type     | 필수여부 | 설 명                                                             |
| ------------- | -------- | ---- | --------------------------------------------------------------- |
| Content       | String   | 필수   | 조회XML 또는 조회JSON 문자열                                             |
| Opt.Append    | Boolean  | 선택   | Append 조회 여부, Default=0                                         |
| Opt.AppendRow | Number   | 선택   | Append 조회 시 데이터를 붙여넣을 위치 설정                                     |
| Opt.CalBack   | Function | 선택   | CallBack 함수                                                     |
| Opt.Event     | Boolean  | 선택   | 완료 이벤트 발생 여부 Default = 1                                        |
| Opt.Fx        | Boolean  | 선택   | 포맷팅된 데이터 조회 처리 여부, Default=0                                    |
| Opt.Sync      | Boolean  | 선택   | 동기 조회 여부 이 함수는 기본적으로 비동기 형태로 동작한다. Default=0                    |
| Opt.Wait      | Boolean  | 선택   | 대기 이미지 표시 여부 동기 조회인 경우에는 설정값에 상관없이 대기 이미지를 표시하지 않는다. Default=1, |

- **Example**

```javascript
//1. 조회된 데이터가 없음을 로딩
var data = {Data:[]};
mySheet.LoadSearchData(data);
//2. 서버로부터 데이터를 가져와 로딩
//조회 데이터 읽어오기
var sXml = mySheet.GetSearchData(" list.jsp","sa_nm=chris&sa_no=2007128");
//조회 결과 내용을 표현하기
mySheet.LoadSearchData(sXml);
// 조회 결과 내용을 기존데이터에 Append 하여 표현하기
var opt = { Append : 1 };
mySheet.LoadSearchData(sXml, opt);
```

- **제공 버전**

|  **7.0.0.0**  |                                      |
|:-------------:|--------------------------------------|
|  **7.0.5.4**  | Fx:2 옵션 추가                       |
|  **7.0.6.0**  | 대기이미지 표시여부 속성 추가 (Wait) |
| **7.0.13.43** | CallBack, Event 속성 추가            |