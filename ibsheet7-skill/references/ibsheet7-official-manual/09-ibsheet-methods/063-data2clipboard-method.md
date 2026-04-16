# Data2Clipboard Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > Data2Clipboard Method

---

- **기능**

> IBSheet위의 있는 모든 데이터를 클립보드에 복사한다. 이 함수를 호출하면 헤더를 포함하여 데이터 부분과 합계 부분까지 모든 데이터를 복사하며, 컬럼과 컬럼사이는 탭으로 구분하고, 행과 행사이는 줄바꿈으로 구분하여 클립보드에 복사한다.
>
> **해당 기능은 브라우저별 Clipboard 보안 상 IE 브라우저에서만 사용이 가능 하다.**

- **Syntax**

|        |                            |
|:------:|----------------------------|
| Syntax | ObjId.**Data2Clipboard**() |

- **Info**

> **Return**: String, 클립보드에 복사된 문자열

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```
//클립보드에 복사한다.
mySheet.Data2Clipboard();
```

- **제공 버전**

> **7.0.0.0**