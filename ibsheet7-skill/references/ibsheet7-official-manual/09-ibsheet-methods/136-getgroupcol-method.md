# GetGroupCol Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetGroupCol Method

---

- **기능**

> 현재 설정되어있는 그룹 기준 컬럼을 SaveName확인한다.
>
> 2개 이상의 컬럼이 설정되어 있는 경우는 "\|"를 구분자로 하여 연결된 문자열로 리턴 된다.

- **Syntax**

|        |                         |
|:------:|-------------------------|
| Syntax | ObjId.**GetGroupCol**() |

- **Info**

> **Return**: String, 현재 설정된 그룹 기준 컬럼 정보

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```javascript
// 그룹행을 설정한다.
mySheet.ShowGroupRow();
// 현재 설정되어 있는 그룹 기준 컬럼을 확인한다
var Cols = mySheet.GetGroupCol();
```

- **제공 버전**

> **7.0.0.0**
>
> **  **