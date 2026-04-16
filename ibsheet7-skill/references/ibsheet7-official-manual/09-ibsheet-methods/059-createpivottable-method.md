# CreatePivotTable Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CreatePivotTable Method

---

- **기능**

> 피벗 테이블은 대화형 테이블의 일종으로, 데이터의 나열 형태에 따라서 합계나 카운트 등의 계산을 하는 기능이다.
>
> 데이터가 있는 IBSheet의 값이 변경되더라도 피벗 테이블에 자동 반영되지 않으므로 원하는 시점에 이 메소드를 다시 호출 하여야 한다.

- **Syntax**

|        |                                             |
|:------:|---------------------------------------------|
| Syntax | ObjId.**CreatePivotTable**(Info, DataSheet) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                      |
| --------- | ------ | ---- | ------------------------ |
| Info      | json   | 필수   | 피벗 테이블 설정 객체 집합 (세부내용참고) |
| DataSheet | Object | 필수   | 원본 데이터가 있는 IBSheet의 객체   |

> **세부내용**
>
> Info에 설정 할 수 있는 속성은 다음과 같다.

| 속성              | 타입      | 설명                                                                                                                                                         |
| --------------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Cols            | String  | 열 레이블 필드에 설정할 ‘\|'로 구분된 Column Index 또는 SaveName.                                                                                                          |
| DefaultView     | String  | 값이 없는 셀에 보여질 문자열                                                                                                                                           |
| Rows            | String  | 행 레이블 필드에 설정할 ‘\|'로 구분된 Column Index 또는 SaveName.                                                                                                          |
| SortRow         | Boolean | 행 레이블 집계시 정렬후 집계할지 여부. 0으로 설정시 소트를 하지 않고 조회된 데이터 기준으로 행 레이블이 생성된다. 1로 설정시 조회된 데이터를 정렬후에 행 레이블을 생성한다.(기본값 : 1)                                              |
| Value           | String  | 합계 또는 카운트할 ‘\|'로 구분된 Column Index 또는 SaveName.                                                                                                             |
| ValueType       | String  | ‘\|'로 구분된 합계행 타입. (‘Sum' 합계, ‘Count' 개수) Value 의 개수와 동일해야 한다.                                                                                              |
| AutoFitColWidth | String  | FitColWidth에 대한 적용 시점 설정 적용하고자 하는 설정값을 구분자 "\|" 로 연결하여 설정한다. (Default : "") 세부 설명은 SetConfig Method 참고                                                     |
| CalcSumRatio    | Number  | 합계 비율 모드 (Default : 0) \| 설정 값 \| 설명      \| \| ---- \| ------- \| \| 0    \| 기본 합계   \| \| 1    \| 총 합계 비율 \| \| 2    \| 열 합계 비율 \| \| 3    \| 행 합계 비율 \| |

- **Example**

```
//5,6,7 열을 행 레이블 필드로 설정하고, 8,9,10 열을 열 레이블의 필드로 설정하여, 13 컬럼을 요약정보(합계)에 표시한다.
mySheet2.CreatePivotTable({Rows:'5|6|7', Cols:'8|9|10', Value:'13', ValueType:'Sum'}, mySheet);
// 5,6,7 열을 행 레이블 필드로 설정하고, 2 열을 열 레이블의 필드로 설정하여, 13 컬럼을 요약정보(개수)에 표시한다.
mySheet2.CreatePivotTable({Rows:'5|6|7', Cols:'2', Value:'13', ValueType:'Count'}, mySheet);
```

- **제공 버전**

| **7.0.0.0**  |                                              |
|:------------:|----------------------------------------------|
| **7.0.13.0** | AutoFitColWidth, CalcSumRatio 인자 속성 추가 |