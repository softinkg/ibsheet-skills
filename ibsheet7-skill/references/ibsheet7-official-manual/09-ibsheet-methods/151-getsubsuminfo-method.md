# GetSubSumInfo Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetSubSumInfo Method

---

- **기능**

> 현재 시트의 소계 설정 정보를 확인 한다.
>
> SaveName 인자를 설정하지 않거나, 0으로 설정한 경우 컬럼 정보는 Index로 반환 하고, SaveName 인자를 1로 설정한 경우 SaveName으로 반환 한다.
>
> 반환되는 값은 객체 배열 형태로 [ShowSubSum](#showsubsum-method) 메소드의 인자 형태와 동일 하다.

- **Syntax**

|        |                                   |
|:------:|-----------------------------------|
| Syntax | ObjId.**GetSubSumInfo**(SaveName) |

- **Info**

> **Return**: Object

| Parameter | Type    | 필수여부 | 설 명                     |
| --------- | ------- | ---- | ----------------------- |
| SaveName  | Boolean | 필수   | 컬럼 정보를 SaveName으로 반환 여부 |

- **Example**

```javascript
// 소계 정보 확인 하기 (SaveName)
var subsumInfo = mySheet.GetSubSumInfo(1);
```

- **제공 버전**

| **7.0.13.34** |     |
|---------------|-----|

> **  **