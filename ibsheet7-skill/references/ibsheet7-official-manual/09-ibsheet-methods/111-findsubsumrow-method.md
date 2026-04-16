# FindSubSumRow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > FindSubSumRow Method

---

- **기능**

> ShowSubSum 함수를 이용하여 표시된 소계의 행 번호를 "\|"로 연결하여 문자열로 반환한다. StdCol 인자를 설정하지 않으면 모든 소계 행을 찾고, StdCol을 설정할 경우 해당 컬럼으로 계산된 소계 행만 찾아서 문자열로 반환한다.

- **Syntax**

|        |                                     |
|:------:|-------------------------------------|
| Syntax | ObjId.**FindSubSumRow**([StdCol]) |

- **Info**

> **Return**: String, 소계의 행 번호를 "|"로 연결한 문자열

| Parameter | Type        | 필수여부 | 설 명                                                  |
| --------- | ----------- | ---- | ---------------------------------------------------- |
| StdCol    | Long/String | 선택   | 소계를 표시한 기준 컬럼의 컬럼Index 또는 SaveName. Default=""(전체컬럼) |

- **Example**

```javascript
//표시된 모든 소계의 행 번호를 가져온다.
var sRow = mySheet.FindSubSumRow();
//1컬럼으로 기준으로 표시된 소계 행의 행번호를 가져온다.
var sRow = mySheet.FindSubSumRow(1);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **