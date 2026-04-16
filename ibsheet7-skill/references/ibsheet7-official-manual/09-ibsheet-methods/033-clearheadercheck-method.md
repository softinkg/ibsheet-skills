# ClearHeaderCheck Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ClearHeaderCheck Method

---

- **기능**

> 헤더의 모든 전체체크박스의 값을 언체크로 초기화 한다.
>
> HeaderCheck 메소드와 마찬가지로 전체체크의 기능 처리는 하지 않고 단순 언체크 처리만 한다.

- **Syntax**

|        |                              |
|:------:|------------------------------|
| Syntax | ObjId.**ClearHeaderCheck**() |

- **Info**

> **Return**: None

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```
// RemoveAll 호출전에 전체체크박스를 초기화 한다..
mySheet.ClearHeaderCheck();
mySheet.RemoveAll();
```

- **제공 버전**

7.0.0.0