# LastCol Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > LastCol Method

---

- **기능**

> 마지막 컬럼의 index를 반환한다.

- **Syntax**

|        |                     |
|:------:|---------------------|
| Syntax | ObjId.**LastCol**() |

- **Info**

> **Return**: Long, 마지막 컬럼 인덱스

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```
//마지막 컬럼의 index를 확인한다.
Alert("마지막 컬럼의 index는 " + mySheet.LastCol() + " 번 입니다.");
```

- **제공 버전**

> **7.0.0.0**
>
> **  **