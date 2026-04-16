# DoRowSearch Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DoRowSearch Method

---

- **기능**

> 특정 행의 셀 데이터를 조회 한다.

- **Syntax**

|        |                                                         |
|:------:|---------------------------------------------------------|
| Syntax | ObjId.**DoRowSearch**(Row, PageUrl, [Param], [Opt]) |

- **Info**

> **Return**: None

| Parameter     | Type    | 필수여부 | 설 명                                                                                                                                                                                 |
| ------------- | ------- | ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Row           | Long    | 필수   | 대상 행의 Index                                                                                                                                                                         |
| PageUrl       | String  | 필수   | 처리할 페이지 Url                                                                                                                                                                         |
| Param         | String  | 선택   | 조회조건 Query String, Default ""                                                                                                                                                       |
| Opt.ReqHeader | Object  | 선택   | 요청헤더 설정 값 객체, Default={}                                                                                                                                                            |
| Opt.Sync      | Boolean | 선택   | 동기 조회 여부 Default=0 (SearchSync 설정 시 SearchSync 값) \| 설정값 \| 설명           \| \| --- \| ------------ \| \| 0   \| 비동기 방식       \| \| 1   \| 비동기 순차 처리 방식 \| \| 2   \| 동기 방식        \| |
| Opt.Wait      | Boolean | 선택   | 대기 이미지 표시 여부, Default =1                                                                                                                                                            |

- **Example**

```javascript
//3컬럼의 데이터가 바뀌었을 때 해당 행의 데이터를 DB에서 읽어옴
function mySheet_OnChange(Row, Col, Value) {
if (Col == 3) {
var opt = { Wait : 1, Sync : 1 };
mySheet.DoRowSearch(Row, "grid_rowdata.html", "" , opt);
}
}
// 1. 이미지 미표시, 비동기 조회
var opt = { Wait : 0, Sync : 0 };
mySheet.DoRowSearch(Row, "grid_rowdata.html", "" , opt);
// 2. 이미지 표시, 비동기 순차처리 조회
var opt = { Wait : 1, Sync : 1 };
mySheet.DoRowSearch(Row, "grid_rowdata.html", "" , opt);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **