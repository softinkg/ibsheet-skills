# OnVScroll Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnVScroll Event

---

- **기능**

> 세로스크롤 시 이벤트가 발생한다.

- **Syntax**

|  |  |
|:--:|----|
| Syntax | **function 오브젝트ID_OnVScroll**(vpos, oldvpos, isTop, isBottom) { } |

- **Parameters**

|           |         |                                        |
|:---------:|:-------:|:--------------------------------------:|
| Parameter |  Type   |                 설 명                  |
|   vpos    |  Long   |             세로 스크롤 값             |
|  oldvpos  |  Long   |          이전 세로 스크롤 값           |
|   isTop   | Boolean | 세로 스크롤이 최상단에 위치했는지 여부 |
| isBottom  | Boolean | 세로 스크롤이 최하단에 위치했는지 여부 |

- **Example**

```javascript
function mySheet_OnVScroll(vpos, oldvpos, isTop, isBottom) {
}
```

- **제공 버전**

7.0.0.0