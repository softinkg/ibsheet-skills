# OnMovePage Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnMovePage Event

---

- **기능**

> smClientPaging 모드에서 페이지 네비게이션 또는 페이지 이동 메소드를 통해 페이지를 이동하는 경우 이동 전에 이벤트가 발생 한다.

- **Syntax**

|        |                                                        |
|:------:|--------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnMovePage** (Current, Move) { } |

- **Parameters**

|           |        |                                  |
|:---------:|:------:|:--------------------------------:|
| Parameter |  Type  |              설 명               |
|  Current  | Number | 페이지 이동전의 현재 페이지 번호 |
|   Move    | Number |        이동할 페이지 번호        |

- **Example**

```javascript
function mySheet_OnMovePage(current, move) {
// 페이지 이동 후 경고창을 띄운다.
Alert(“페이지 이동 했습니다.”);
}
```

- **제공 버전**

| **7.0.13.116** |     |
|----------------|-----|