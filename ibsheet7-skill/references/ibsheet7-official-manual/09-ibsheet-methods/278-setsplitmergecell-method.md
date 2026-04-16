# SetSplitMergeCell Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SetSplitMergeCell Method

---

- **기능**

> 셀 병합(머지) 되어 있는 셀 영역을 취소(분할) 처리 한다.
>
> 동일한 값에 의한 자동 머지 또는 SetMergeCell 메소드를 이용한 머지에 대해서 취소 할 수 있다.
>
> 최소 한 경우 각 셀의 값은 셀 병합(머지) 이전의 값을 유지하게 된다.

- **Syntax**

|        |                                       |
|:------:|---------------------------------------|
| Syntax | ObjId.**SetSplitMergeCell**(Row, Col) |

- **Info**

> **Return**: None

| Parameter | Type           | 필수여부 | 설 명                        |     |
| --------- | -------------- | ---- | -------------------------- | --- |
| Row       | Number         | 필수   | 대상 셀의 행 Index              |     |
| Col       | Number/ String | 필수   | 대상 셀의 컬럼 Index 또는 SaveName |     |

- **Example**

```
// (1,1)부터(2,2)까지 2x2 셀 병합 영역을 분할 한다.
mySheet.SetSplitMergeCell(1, 1);
```

- **제공 버전**

7.0.0.0