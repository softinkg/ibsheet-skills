# OnBeforeCheckAll Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnBeforeCheckAll Event

---

- **기능**

> 사용자의 마우스 클릭을 통한 의한 헤더의 전체체크박스의 값 변경시 전체체크 처리 이전에 이벤트가 발생한다.
>
> 이벤트의 리턴값을 false로 설정하는 경우 전체체크 처리는 취소 된다.

- **Syntax**

|        |                                                        |
|:------:|--------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnBeforeCheckAll**(Row, Col) { } |

- **Parameters**

|           |        |                        |
|:---------:|:------:|:----------------------:|
| Parameter |  Type  |         설 명          |
|    Row    | Number |  해당 셀의 Row Index   |
|    Col    | Number | 해당 셀의 Column Index |

- **Example**

```javascript
// confirm 을 통한 전체체크 제어
function mySheet_OnBeforeCheckAll(Row, Col) {
if (!confirm("전체체크를 진행하시겠습니까?") {
// 진행 취소 처리
return false;
}
}
```

- **제공 버전**

| **7.0.1.0** |     |
|-------------|-----|