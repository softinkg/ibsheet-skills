# ColCondProperty Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ColCondProperty Method

---

- **기능**

> 숫자형 타입에서 특정 컬럼의 각 셀의 데이타값이 조건에 맞을경우 속성을 설정, 설정한 조건을 확인한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 모든행에 대해서 처리를 하고 SaveName으로 설정할 경우 해당 SaveName이 포함된 행에 대해서만 처리 한다.
>
> 이 함수를 통해 설정이 가능한 속성은 다음과 같다.

| 속성       | 타입    | 설명                                   |
|------------|---------|----------------------------------------|
| BackColorT | String  | 조건이 True 인경우 배경색상            |
| BackColorF | String  | 조건이 False 인경우 배경색상           |
| FontColorT | String  | 조건이 True 인경우 폰트색상            |
| FontColorF | String  | 조건이 False 인경우 폰트색상           |
| EditT      | Boolean | 조건이 True 인경우 편집여부            |
| EditF      | Boolean | 조건이 False 인경우 편집여부           |
| CursorT    | String  | 조건이 True 인경우 마우스 포인터 설정  |
| CursorF    | String  | 조건이 False 인경우 마우스 포인터 설정 |

> 설정할수 있는 마우스 모양은 아래와 같다.

|         |                  |
|:-------:|:----------------:|
| 설정값  |   마우스 모양    |
| Default | 기본 화살표 모양 |
| Pointer |   손가락 모양    |

- **Syntax**

|        |     |                                   |
|:------:|:---:|-----------------------------------|
| Syntax | Get | ObjId.**GetColCondProperty**(Col) |

- **Info**

> **Return**: String, 설정한 조건 (Get Method 인 경우)

| Parameter | Type          | 필수여부 | 설 명                         |
| --------- | ------------- | ---- | --------------------------- |
| Col       | Long / String | 필수   | 대상이 되는 컬럼 index 또는 SaveName |

- **Example**

```
// 설정한 조건을 확인한다.
mySheet.GetColCondProperty(13)
```

- **Syntax**

|        |     |                                               |
|:------:|:---:|-----------------------------------------------|
| Syntax | Set | ObjId.**SetColCondProperty**(Col, Cond, Prop) |

- **Info**

> **Return**: None

| Parameter | Type          | 필수여부 | 설 명                         |
| --------- | ------------- | ---- | --------------------------- |
| Col       | Long / String | 필수   | 대상이 되는 컬럼 index 또는 SaveName |
| Cond      | String        | 필수   | 설정할 조건 (예:"%d >1000")       |
| Prop      | Object        | 선택   | 설정할 컬럼 속성                   |

- **Example**

```
// 13번째 컬럼의 각 셀 데이터 값이 1000 보다 클경우
mySheet.SetColCondProperty(13,"%d>1000",{BackColorT:"#00ff00",FontColorT:"#ffff00", EditT : false, BackColorF : "#0000ff",FontColorF:"#ffffff", EditF : true, CursorT:"Pointer", CursorF:"Default"})
```

- **제공 버전**

7.0.0.0