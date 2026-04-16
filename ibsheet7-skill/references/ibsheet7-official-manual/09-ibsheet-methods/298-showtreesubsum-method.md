# ShowTreeSubSum Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ShowTreeSubSum Method

---

- **기능**

> 트리구조에서 특정 컬럼의 데이터를 기준으로 소계를 계산하여 표시한다.
>
> 이 함수는 데이터를 조회하는 메소드를 호출하기 이전에 호출하여야 하며, 설정을 변경한 경우 다시 데이터를 조회하여야 적용된다.
>
> 인자값은 JSON 형태의 포맷으로 설정 한다.
>
> 예) var info = {SumCols:"2\|3\|4", AvgCols:"5\|6", SumEx:1};

- **Syntax**

|        |                                |
|:------:|--------------------------------|
| Syntax | ObjId.**ShowTreeSubSum**(Info) |

- **Info**

> **Return**: None

| Parameter       | Type    | 필수여부 | 설 명                                                           |
| --------------- | ------- | ---- | ------------------------------------------------------------- |
| Info.SumCols    | String  | 선택   | 합계가 계산되어야 할 컬럼의 Index또는 SaveName을 "\|"로 연결한 문자열. Defuault=""  |
| Info.AvgCols    | String  | 선택   | 평균이 계산되어야 할 컬럼의 Index 또는 SaveName을 "\|"로 연결한 문자열. Defuault="" |
| Info.CountCols  | String  | 선택   | 개수가 계산되어야 할 컬럼의 Index 또는 SaveName을 "\|"로 연결한 문자열. Default=""  |
| Info.MaxCols    | String  | 선택   | 최대값이 계산되어야 할 컬럼의 Index 또는 SaveName을 "\|"로 연결한 문자열. Default="" |
| Info.MinCols    | String  | 선택   | 최소값이 계산되어야 할 컬럼의 Index 또는 SaveName을 "\|"로 연결한 문자열. Default="" |
| Info.SumEx      | Boolean | 선택   | 상태값이 "삭제"인 행에 대한 계산 포함 여부. Default=0                          |
| Info.ExceptNull | Boolean | 선택   | 평균 컬럼에서 Null 값 포함 계산 여부. Default=0                            |

- **Example**

```javascript
//2번째 컬럼에 대한 트리 소계 표현
var info = {SumCols: "2"};
mySheet.ShowTreeSubSum(info);
// 삭제행은 계산에서 제외하기
var info = {SumCols: "2", SumEx: "1"};
mySheet.ShowTreeSubSum (info);
```

- **제공 버전**

| **7.0.0.0**  |                                 |
|:------------:|---------------------------------|
| **7.0.12.0** | MaxCols, MinCols 인자 속성 추가 |

> **  **