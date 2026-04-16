# OnHScroll Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnHScroll Event

---

- **기능**

> 가로스크롤 시 이벤트가 발생한다.

- **Syntax**

|  |  |
|:--:|----|
| Syntax | **function 오브젝트ID_OnHScroll**(hpos, oldhpos, isLeft, isRight, section) { } |

- **Parameters**

|           |         |                                         |
|:---------:|:-------:|:---------------------------------------:|
| Parameter |  Type   |                  설 명                  |
|   hpos    |  Long   |             가로 스크롤 값              |
|  oldhpos  |  Long   |           이전 가로 스크롤 값           |
|  isLeft   | Boolean | 가로 스크롤이 좌측 끝에 위치했는지 여부 |
|  isRight  | Boolean | 가로 스크롤이 우측 끝에 위치했는지 여부 |
|  section  |   Int   |     스크롤 섹션값 (항상 1이 반한됨)     |

- **Example**

```javascript
function mySheet_OnHScroll(hpos, oldhpos, isLeft, isRight, section) {
}
```

- **제공 버전**

7.0.0.0