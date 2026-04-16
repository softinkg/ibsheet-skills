# DoSearch Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DoSearch Method

---

- **기능**

> 조회 페이지를 연결하여 조회 XML을 읽어 들이고, XML의 데이터를 IBSheet 내부에 표현한다.
>
> Param 인자는 조회조건을 "조건명1=값1&조건명2=값2" 식으로 "="와 "&"로 조건을 연결하여 설정한다.
>
> Opt 인자는 객체형식의 인자로 동기조회여부(Sync) 와 Append조회여부(Append)를 설정 할 수 있다.
>
> Sync 인자는 동기/비동기 조회 모드이다. 비동기일 경우 연속으로 호출시 이전 조회가 종료되지 않으면 이후의 조회는 모두 무시된다. 연속으로 호출해야 되고, 반드시 모든 조회가 완료되어야 한다면 동기 조회 모드를 사용해야 한다.
>
> Append 인자를 1로 설정하는 경우 기존 데이터에 현재 조회 데이터를 첨부하여 조회 할 수 있다.
>
> Url로 조회 페이지를 호출하고 조회 데이터를 읽어 들여 데이터 표현을 완료한 후 OnSearchEnd 이벤트를 발생하고 처리는 종료된다.

- **Syntax**

|        |                                                 |
|:------:|-------------------------------------------------|
| Syntax | ObjId.**DoSearch**(PageUrl, [Param], [Opt]) |

- **Info**

> **Return**: None

| Parameter     | Type          | 필수여부 | 설 명                                                                                                                                                                                 |
| ------------- | ------------- | ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| PageUrl       | String        | 필수   | 조회 XML 페이지 파일 이름                                                                                                                                                                    |
| Param         | String/ Obect | 선택   | 조회 조건 Query String, Default="" 혹은 조회 조건 JSON                                                                                                                                        |
| Opt.Append    | Boolean       | 선택   | Append 조회 여부, Default=0                                                                                                                                                             |
| Opt.AppendRow | Number        | 선택   | Append 조회 시 데이터를 붙여넣을 위치 설정                                                                                                                                                         |
| Opt.CallBack  | Function      | 선택   | 조회 후 사용자 정의 콜백함수                                                                                                                                                                    |
| Opt.Fx        | Boolean       | 선택   | 포맷팅된 데이터 조회 처리 여부, Default=0                                                                                                                                                        |
| Opt.ReqHeader | Object        | 선택   | 요청헤더 설정 값 객체, Default={}                                                                                                                                                            |
| Opt.Sync      | Boolean       | 선택   | 동기 조회 여부 Default=0 (SearchSync 설정 시 SearchSync 값) \| 설정값 \| 설명           \| \| --- \| ------------ \| \| 0   \| 비동기 방식       \| \| 1   \| 비동기 순차 처리 방식 \| \| 2   \| 동기 방식        \| |

- **Example**

```javascript
// 1. 일반조회
mySheet.DoSearch("list.jsp", "p1=aa&p2=bb");
// 2. 비동기 순차 조회
var opt = { Sync : 1 };
mySheet.DoSearch("list.jsp", "p1=aa&p2=bb", opt);
// 3. Append 조회
var opt = { Append : 1 };
mySheet.DoSearch("list.jsp", "p1=aa&p2=bb", opt);
// 4. Sync && Append 조회
var opt = { Sync : 1, Append : 1 };
mySheet.DoSearch("list.jsp", "p1=aa&p2=bb", opt);
// 5. 요청헤더 설정
var opt = { ReqHeader : { "Prop" : "Value"} };
mySheet.DoSearch("list.jsp", "p1=aa&p2=bb", opt);
// 6. 파라미터 JSON 구조로 설정
var param = {"p1 ":100, "p2":"a"},
opt = {ReqHeader : {"Content-Type":"application/json"}};
mySheet.DoSearch("list.jsp", param, opt);
// or
mySheet.DoSearch("list.jsp", {"p1":100, "p2":"a"}, {ReqHeader : {"Content-Type":"application/json"}} );
```

- **제공 버전**

|  **7.0.0.0**   |                       |
|:--------------:|-----------------------|
| **7.0.13.164** | Param JSON 구조 추가. |

> **  **