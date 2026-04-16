# ComputeSum Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ComputeSum Method

---

- **기능**

> 특정 영역의 합계를 계산하여 반환한다.
>
> 이 속성은 특정 컬럼의 합계만 계산할 수도 있고, 공식을 사용하여 계산 되어진값의 합계를 구할수도 있다. 특정 영역을 지정하지 않으면 모든 데이터의 합계를 계산하여 반환한다.

- **Syntax**

|  |  |
|:--:|----|
| Syntax | ObjId.**ComputeSum**(CalcuLogic,[FirstRow],[LastRow],[isFullSum]) |

- **Info**

> **Return**: Double, 계산되어진 특정역역의 합계

| Parameter  | Type    | 필수여부 | 설 명                                                                 |
| ---------- | ------- | ---- | ------------------------------------------------------------------- |
| CalcuLogic | String  | 필수   | 계산 공식, 공식에 다른 컬럼값이 사용되는 경우 반드시 "\|"로 감싸서 사용한다.                      |
| FirstRow   | Long    | 선택   | 계산 대상행의 시작 index, Default=-1                                        |
| LastRow    | Long    | 선택   | 계산 대상행의 마지막 index, Default=-1                                       |
| isFullSum  | Boolean | 선택   | 해당 계산식을 소계행도 포함할지의 여부, Default=1 1 : 소계행을 계산식에 포함 0 : 소계행은 계산식에서 제외 |

- **Example**

```javascript
//3컬럼의 합계를 구한다.
var Sum3 = mySheet.ComputeSum("|3|");
//1행부터 10행까지 3컬럼 * 4컬럼 / 100 한 값들의 합계를 구한다.
var Sum4 = mySheet.ComputeSum("|3| * |4| / 100", 1, 10);
```

- **제공 버전**

> **7.0.0.0**