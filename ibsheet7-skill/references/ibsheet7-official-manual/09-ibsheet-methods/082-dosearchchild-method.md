# DoSearchChild Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DoSearchChild Method

---

- **기능  **
  트리 형태의 데이터 구조에서 해당행의 자식을 조회하지 않은 상태에서 OnTreeChild 이벤트 안에서 자식데이타를 조회 페이지를 연결하여 조회 XML, JSON을 읽어 들이고, XML, JSON의 데이터를 자식으로 Append 하여 표현한다.

> **Row** 인자는 자식데이타를 Append할 부모 인자를 OnTreeChild 이벤트를 통해서 넘겨준다.
>
> **Url**로 자식데이타로 조회할 페이지를 호출하고 조회 XML, JSON을 읽어 들여 데이터 표현을 완료한 후 OnSearchEnd 이벤트를 발생하고 처리는 종료된다.
>
> **Param** 인자는 조회조건을 "조건명1=값1&조건명2=값2" 식으로 "="와 "&"로 조건을 연결하여 설정한다.
>
> **Wait** 인자는 조회중 대기 이미지 표시 여부를 설정한다.

- **Syntax**

|        |                                                           |
|:------:|-----------------------------------------------------------|
| Syntax | ObjId.**DoSearchChild**(Row, PageUrl, [Param], [Opt]) |

- **Info**

> **Return**: None

| Parameter     | Type    | 필수여부 | 설 명                                                                                                                                                                                                          |
| ------------- | ------- | ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Row           | Long    | 필수   | OnTreeChild 이벤트에서 받은 행의 Index                                                                                                                                                                                |
| PageUrl       | String  | 필수   | 조회 XML,JSON 페이지 파일 이름                                                                                                                                                                                        |
| Param         | String  | 선택   | 조회 조건 Query String, Default=""                                                                                                                                                                               |
| Opt.ReqHeader | Object  | 선택   | 요청헤더 설정 값 객체, Default={}                                                                                                                                                                                     |
| Opt.Sync      | Boolean | 선택   | 동기 조회 여부 (동기상태에서는 대기이미지가 표시되지 않음) Default=0 (SearchSync 설정 시 SearchSync 값) \| 설정값 \| 설명           \| \| --- \| ------------ \| \| 0   \| 비동기 방식       \| \| 1   \| 비동기 순차 처리 방식 \| \| 2   \| 동기 방식        \| |
| Opt.Wait      | Boolean | 선택   | 대기 이미지 표시 여부, Default=1                                                                                                                                                                                      |

- **Example**

```javascript
// 자식데이터 조회하기
<script type="text/Javascript">
function mySheet_OnTreeChild(Row){
var url = "";
// 4컬럼 : 트리컬럼
switch(mySheet.GetCellValue(Row, 4)){
case "서울" :
url = " type15_dat(1).xml";
break;
case "인천":

url = "type15_data(2).xml";
break;
}
var opt = { Wait : 1, Sync : 0 };
mySheet.DoSearchChild(Row, url, "", opt);
}
</script>
// 1. 이미지 표시, 비동기 조회
var opt = { Wait : 1 Sync : 0 };
mySheet.DoSearchChild(Row, url, "", opt);
// 2. 이미지 미표시, 비동기 순차 조회 (비동기 순차 조회 선택시 대기이미지는 보여지지 안음)
var opt = { Wait : 0, Sync : 1 };
mySheet.DoSearchChild(Row, url, "", opt);
// 파라미터 JSON 구조로 설정
var param = {"p1 ":100, "p2":"a"},
var opt = {ReqHeader : {"Content-Type":"application/json"}};
mySheet. DoSearchChild (Row, url, param, opt);
```

- **제공 버전**

|  **7.0.0.0**   |                       |
|:--------------:|-----------------------|
| **7.0.13.164** | Param JSON 구조 추가. |

> **  **