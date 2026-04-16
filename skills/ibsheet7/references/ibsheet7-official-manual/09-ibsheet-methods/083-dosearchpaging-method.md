# DoSearchPaging Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DoSearchPaging Method

---

- **기능**

> 대량 데이터를 조회 하고자 하는 경우 IBSheet 의 스크를 위치의 데이터 일부만을 조회 하여 화면에 표현한다.
>
> 스크롤의 위치를 변경할 때마다 인자로 설정된 Url이 호출되며 데이터를 해당 위치에 표현한다.
>
> 해당 기능 사용시 초기화 함수인 SetConfig 에서 SearchMode를 3으로 설정하고 Page 속성을 반드시 설정하여야 한다.
>
> 전체 스크롤 사이즈는 조회 데이터의 Total 속성 설정값을 따르며, Total 속성 값을 반드시 설정 하여야 한다.
>
> 해당 기능으로 조회시 Row 및 Cell의 속성, 멀티 트랜잭션 기능 사용에 제약이 따른다.

- **Syntax**

|        |                                        |
|:------:|----------------------------------------|
| Syntax | ObjId.**DoSearchPaging**(Url, [Opt]) |

- **Info**

> **Return**: None

| Parameter         | Type           | 필수여부 | 설 명                                                                                                                                                       |
| ----------------- | -------------- | ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Url               | String         | 필수   | 조회 페이지 Url                                                                                                                                                |
| Opt.PageParam     | String         | 선택   | 페이지 인덱스를 받을 변수명, Default="ibpage"                                                                                                                         |
| Opt.Param         | String/ Object | 선택   | 조회 조건 Query String, Default="" 혹은 조회 조건 JSON                                                                                                              |
| Opt. OrderbyParam | String         | 선택   | 헤더 정렬 정보를 받을 변수명, Default="iborderby" 값은 "SIDO\|SIGUNGU ^ASC\|DESC" 와 같이 savename 과 정렬 방향이 "^"로 구분되며 각 이름은 "\|"로 구분되어 있다.                                 |
| Opt. UseWaitImage | Boolean        | 선택   | WaitImageVisible 설정이 true 일때 2페이지 이상 조회시 대기 이미지 표시 여부. Default=0                                                                                          |
| Opt.ReqHeader     | Object         | 선택   | 요청헤더 설정 값 객체, Default={}                                                                                                                                  |
| Opt.Sync          | Boolean        | 선택   | 동기 조회 여부 Default=0 (SearchSync 설정 시 SearchSync 값) \| 설정값 \| 설명           \| \| --- \| ------------ \| \| 0   \| 비동기 방식       \| \| 1   \| 비동기 순차 처리 방식 \| |
| Opt.CPage         | Number         | 선택   | 특정 페이지를 기준으로 조회.                                                                                                                                          |

- **Example**

```javascript
//초기화 설정 (페이지 사이즈를 100으로 설정)
var cfg = {SearchMode:3, Page:100};
mySheet.SetConfig(cfg);
// 실시간 조회
var info = {PageParam: "page", OrderbyParam:"orderbyParam", Param: "id=ibleaders&seq=1"};
mySheet.DoSearchPaging("list.jsp",info);
// 비동기 순차 조회
var info = {PageParam: "page", OrderbyParam:"orderbyParam", Param: "id=ibleaders&seq=1", Sync : 1};
mySheet.DoSearchPaging("list.jsp",info);
// Param JSON 구조로 설정
var param = { "Param":{"p1":100, "p2":"aa"} , "ReqHeader":{"Content-Type":"application/json"} };
mySheet.DoSearchPaging("list.jsp", param);
```

- **제공 버전**

|  **7.0.0.0**   |                       |
|:--------------:|-----------------------|
| **7.0.13.151** | CPage 속성 추가.      |
| **7.0.13.157** | Param JSON 구조 추가. |

> **  **