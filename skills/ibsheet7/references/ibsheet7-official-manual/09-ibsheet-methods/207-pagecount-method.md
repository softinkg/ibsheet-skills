# PageCount Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > PageCount Method

---

- **기능**

> 조회 모드(SearchMode)에서 사용되는 Page 속성의 값을 설정하거나 확인 한다.

- **Syntax**

|        |     |                          |
|:------:|:---:|--------------------------|
| Syntax | Get | ObjId.**GetPageCount**() |

- **Info**

> **Return**: Number, Page 개수 설정값

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 현재 설정된 페이지 개수를 확인 한다..
mySheet.GetPageCount()
```

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Set | ObjId.**SetPageCount**(Page) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명        |
| --------- | ------ | ---- | ---------- |
| Page      | Number | 필수   | 설정할 페이지 개수 |

- **Example**

```
// 페이지 개수를 50으로 설정 한다.
mySheet.SetPageCount(50);
```

- **제공 버전**

| **7.0.2.0** |     |
|-------------|-----|

> **  **