# OnChangeFilter Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnChangeFilter Event

---

- **기능**

> 필터행의 셀의 값을 바꾸거나 옵션이 변경되었을 때 이벤트가 발생한다.
>
> 사용자의 값 변경외에도, SetFilterOption 함수를 이용했을때도 이벤트가 발생하게 된다.

- **Syntax**

|        |                                              |
|:------:|----------------------------------------------|
| Syntax | **function 오브젝트ID_OnChangeFilter**() { } |

- **Parameters**

| Parameter | Type | 설 명 |
| --------- | ---- | --- |
| **None**  |      |     |

- **Example**

```javascript
//SearchMode:3 일때 필터링 조건이 바뀌게 되면 조회
function mySheet_OnChangeFilter() {
// 필터행 QueryString 변환
var fp = mySheet.GetFilterParam(0,1);
var info = {PageParam: "page", Param: "id=ibleaders&seq=1&" + fp};
mySheet.DoSearchPaging("list.jsp",info);
}
```

- **제공 버전**

7.0.0.0