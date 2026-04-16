# GoToLastPage Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GoToLastPage Method

---

- **기능**

> 페이징 모드로 설정되어 있는 경우 맨 마지막 페이지로 이동한다.
>
> 이 기능을 사용하기 위해서는 SetConfig 함수에서 SearchMode를 페이징 모드로 설정 하여야 한다.

- **Syntax**

|        |                          |
|:------:|--------------------------|
| Syntax | ObjId.**GoToLastPage**() |

- **Info**

> **Return**: Boolean

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```javascript
// 페이징 모드 설정
var cfg = {SearchMode:1, Page:10};
mySheet.SetConfig(cfg);
// 맨 마지막 페이지로 이동
mySheet.GoToLastPage();
```

- **제공 버전**

> **7.0.0.0**