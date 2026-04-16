# HideSubSum Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > HideSubSum Method

---

- **기능**

> ShowSubSum 함수를 호출하면 다음 조회시 조회 데이터 사이에 소계행이 삽입된다. 이 메서드를 사용하면 ShowSubSum에서 시작한 소계기능을 다음 조회에서 더 이상 추가되지 않도록 한다.
>
> 이 메서드는 호출 즉시 동작하는 것이 아니라, 다음 조회시에 반영된다.

- **Syntax**

|        |                                  |
|:------:|----------------------------------|
| Syntax | ObjId.**HideSubSum**([StdCol]) |

- **Info**

> **Return**: None

| Parameter | Type        | 필수여부 | 설 명                                                  |
| --------- | ----------- | ---- | ---------------------------------------------------- |
| StdCol    | Long/String | 선택   | 소계를 표시한 기준 컬럼의 컬럼Index 또는 SaveName. Default=""(전체컬럼) |

- **Example**

```javascript
//1컬럼을 중심으로 소계 계산하여 표시하기
var info = [{StdCol:1, SumCols:"3|4|5"}];
mySheet.ShowSubSum(info);
//표시된 소계 숨기기
mySheet.HideSubSum();
```

- **제공 버전**

7.0.0.0