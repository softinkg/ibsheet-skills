# CurrentColInfo Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CurrentColInfo Method

---

- **기능**

> 현재 IBSheet 컬럼들의 위치, 숨김, 너비 정보를 확인하거나 설정 한다.
>
> 확인시 반환되는 값은 저장용도로만 사용이 가능 하다.
>
> 헤더 메뉴의 "컬럼 정보 저장"을 통해 컬럼들의 정보를 localstorage에 저장하는 기능을 제공하는데, 이 기능을 localstorage 이외의 다른 저장 매체를 이용할때 이 기능을 사용 한다.

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Get | ObjId.**GetCurrentColInfo**() |

- **Info**

> **Return**: String, 현재 컬럼들의 정보

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```javascript
// 현재 컬럼들의 정보를 확인 한다.
var colInfo = mySheet.GetCurrentColInfo()
```

- **Syntax**

|        |     |                                   |
|:------:|:---:|-----------------------------------|
| Syntax | Set | ObjId.**SetCurrentColInfo**(Info) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명           |
| --------- | ------ | ---- | ------------- |
| Info      | String | 필수   | 설정할 컬럼 정보 문자열 |

- **Example**

```
// 이전 컬럼 정보를 설정 한다.
mySheet.SetCurrentColInfo(prevColinfo)
```

- **제공 버전**

| **7.0.13.30** |     |
|---------------|-----|