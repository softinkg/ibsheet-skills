# MergeSheet Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > MergeSheet Method

---

- **기능**

> 전체적인 머지 종류를 설정하거나 확인한다.
>
> 전체 머지가 되지 않는 경우 어떤 셀도 머지 되지 않으며, 전체 머지 가능 상태에서 가로, 세로 머지 가능 여부를 설정하여 머지 되도록 한다.

- **머지된 데이터는 SetConfig에서 설정한 Page 크기에 의해 나누어 진다. 단 머지 유형이 msPrevColumnMerge을 사용하는 경우에는 SetConfig에 PrevColumnMergeMode:0 를 설정하면 앞컬럼 기준으로 머지된 데이터를 표현할 수 있다. 하지만 이 방식은 한번에 머지된 행을 모두 화면 위로 올리므로 머지된 행의 게수가 많아지면 속도가 저하될 수 있다.**

> SetConfig Method의 MergeSheet 설정과 동일한 기능을 한다.

| 상수값 | 종류                               | 설명                                                                    |
| --- | -------------------------------- | --------------------------------------------------------------------- |
| 0   | msNone                           | 머지 없음                                                                 |
| 1   | msAll                            | 전부 머지 가능                                                              |
| 2   | msPrevColumnMerge                | 앞 컬럼이 머지 된 경우 해당 행 안에서 머지 가능                                          |
| 3   | msFixedMerge                     | 단위데이터 행 구조에서 고정 셀 병합 기능                                               |
| 4   | msBaseColumnMerge                | 기준컬럼 머지 영역 범위 내에서 머지 처리 기능 (좌측으로부터 첫번째 ColMerge 속성이 1인 컬럼이 기준컬럼이 된다.) |
| 5   | msHeaderOnly                     | 헤더만 머지                                                                |
| 7   | msPrevColumnMerge + msHeaderOnly | 앞 컬럼이 머지 된 경우 해당 행 안에서 머지기능 + 헤더 머지                                   |
| 8   | msFixedMerge + msHeaderOnly      | 단위데이터 행 구조에서 고정 셀 병합 기능 + 헤더 머지                                       |
| 9   | msBaseColumnMerge + msHeaderOnly | 기준컬럼 머지 영역 범위 내에서 머지 처리 기능 + 헤더 머지                                    |

- **Syntax**

|        |     |                           |
|:------:|:---:|---------------------------|
| Syntax | Get | ObjId.**GetMergeSheet**() |

- **Info**

> **Return**: Integer, 현재 설정된 머지 종류 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//머지 방식 확인
mySheet.GetMergeSheet();
```

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Set | ObjId.**SetMergeSheet**(Merge) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명   |
| --------- | ------- | ---- | ----- |
| Merge     | Integer | 필수   | 머지 종류 |

- **Example**

```
//초기 로드 시 전체 머지 종류를 설정
mySheet.SetMergeSheet( msHeaderOnly);
```

- **제공 버전**

7.0.0.0