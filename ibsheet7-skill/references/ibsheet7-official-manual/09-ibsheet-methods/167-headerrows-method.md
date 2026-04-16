# HeaderRows Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > HeaderRows Method

---

- **기능**

> 헤더행의 개수를 확인한다.
>
> 이 속성은 InitHeaders() 함수를 통해서 설정된 헤더 행의 개수를 의미한다

- **Syntax**

|        |                        |
|:------:|------------------------|
| Syntax | ObjId.**HeaderRows**() |

- **Info**

| Type      | Long, 헤더행의 개수 |     |
| --------- | ------------- | --- |
| Parameter | Type          | 설 명 |
| 없음        |               |     |

- **Example**

```
//헤더 행의 개수를 확인한다.
Alert("헤더 행의 개수는 " + mySheet.HeaderRows() + "개 입니다.");
```

- **제공 버전**

> **7.0.0.0**
>
> **  **