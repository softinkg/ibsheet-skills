# 8.1 Event 사용

> **IBSheet7 개발자 가이드** > IBSheet Events > 8.1 Event 사용

---

> IBSheet에서의 사용자가 원하는 기능을 추가 또는 변경 처리할 수 있도록 다양한 이벤트를 제공한다.

|                                               |
|-----------------------------------------------|
| Function 오브젝트ID_이벤트명(파라미터, …) { } |

> 예를 들어 IBSheet ObjectID를 "mySheet"라 하고, OnChange 이벤트에 대해 기능 처리를 해야 한다면 다음과 같이 기술할 수 있다.

```javascript
Function mySheet_OnChange(Row, Col, Value) {
alert(Row + "," + Col + "의 값이 변경되었습니다.");
}
```

> IBSheet가 제공하는 이벤트는 다음과 같다.