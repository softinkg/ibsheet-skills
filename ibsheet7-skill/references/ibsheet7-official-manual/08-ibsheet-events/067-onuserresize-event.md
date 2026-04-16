# OnUserResize Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnUserResize Event

---

- **기능**

> End-User가 마우스를 이용하여 상단 헤더의 컬럼 너비를 변경할때 이벤트가 발생한다.

- **Syntax**

|        |                                                      |
|:------:|------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnUserResize**(Col, Width) { } |

- **Parameters**

|           |      |                   |
|:---------:|:----:|:-----------------:|
| Parameter | Type |       설 명       |
|    Col    | Long | 해당 Column Index |
|   Width   | Long |  해당 컬럼 너비   |

- **Example**

```javascript
function mySheet_OnUserResize(Col, Width) {
alert(Col + "컬럼의 너비가 " + Width + "로 변경되었습니다".)
}
```

- **제공 버전**

7.0.0.0