# GetCurrentPage Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetCurrentPage Method

---

- **기능**

> 조회 방식이 smGeneral 이 아닌 경우 전체데이터를 기준으로 현재 화면 위에 올려진 부분이 몇번째 페이지인지를 리턴한다.

- **Syntax**

|        |                            |
|:------:|----------------------------|
| Syntax | ObjId.**GetCurrentPage**() |

- **Info**

|        |                           |
|:------:|---------------------------|
| Return | Integer, 현재 페이지 번호 |

- **Example**

```javascript
// 현재 페이지 넘버.
var pageNum = mySheet.GetCurrentPage();
```

- **제공 버전**

> **7.0.0.0**
>
> **  **