# UserAgent Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > UserAgent Method

---

- **기능**

> 조회나 저장시 HTTP 헤더 정보에 포함되어 넘어가는 IBUserAgent의 값을 확인하거나 설정한다.

- **Syntax**

|        |     |                          |
|:------:|:---:|--------------------------|
| Syntax | Get | ObjId.**GetUserAgent**() |

- **Info**

> **Return**: String, 현재 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// IBUserAgent의 값을 확인한다.
mySheet.GetUserAgent();
```

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Set | ObjId.**SetUserAgent**(Value) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명            |
| --------- | ------ | ---- | -------------- |
| Value     | String | 필수   | User-Agent 설정값 |

- **Example**

```
// HTTP 헤더정보의 IBUserAgent 값을 My Agent Name 으로 전송
mySheet.SetUserAgent("My Agent Name");
```

- **제공 버전**

> **7.0.0.0  **