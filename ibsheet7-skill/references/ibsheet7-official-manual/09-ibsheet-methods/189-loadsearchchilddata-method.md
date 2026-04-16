# LoadSearchChildData Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > LoadSearchChildData Method

---

- **기능**

> DoSearchChild 메소드의 기능을 url이 아닌 객체 또는 문자열로 처리하는 기능으로 트리구조에서 자식노드 조회 데이터(xml or json)를 함수의 인자로 전달 받아 아이비시트에 로딩한다. 이 함수는 보안 모듈이 사용 될 경우 복호화된 조회 데이터를 읽어 들이기 위한 것이다. 조회 데이터는 GetSearchData 함수를 통해 서버로부터 가져올 수 있고, 가져온 데이터 문자열을 이 함수의 인자로 설정하면 조회 데이터를 아이비시트에 로딩하고, OnSearchEnd 이벤트를 발생한다.

- **Syntax**

|        |                                                   |
|:------:|---------------------------------------------------|
| Syntax | ObjId.**LoadSearchChildData**(Row, Data, [Opt]) |

- **Info**

> **Return**: None.

| Parameter | Type            | 필수여부 | 설 명                      |
| --------- | --------------- | ---- | ------------------------ |
| Row       | Long            | 필수   | 대상 부모의 행 인덱스             |
| Data      | String / Object | 필수   | 조회 데이터 문자열 또는 JSON 객체    |
| Opt       | Object          | 선택   | 옵션 인자 기능을 json 형태로 설정한다. |

> Opt 옵션 인자 속성은 다음과 같다.

|         |         |                                            |
|:-------:|:-------:|--------------------------------------------|
| WaitDlg | Boolean | 대기이미지 표시 여부 (Default=1)           |
| Append  | Boolean | 기존 자식 데이터에 Append 여부 (Default=0) |

- **Example**

```javascript
//조회 데이터 읽어오기
var Row = mySheet.GetSelectRow();
var Data;
Data=mySheet.GetSearchData(‘list2_Child_Json.jsp', ‘ChildLevel='+(parseInt(mySheet.GetRowLevel(Row))+1));
var Opt = {Append: 1, WaitDlg: 1};
//조회 결과 내용을 표현하기
mySheet.LoadSearchChildData(Row, Data, Opt);
```

- **제공 버전**

7.0.0.0