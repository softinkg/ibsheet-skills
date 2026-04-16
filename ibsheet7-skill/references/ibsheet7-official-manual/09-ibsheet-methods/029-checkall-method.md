# CheckAll Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CheckAll Method

---

- **기능**

> CheckBox가 존재하는 컬럼의 모든 CheckBox를 전체 Check하거나 UnCheck 처리한다.
>
> 이 속성은 사용자가 헤더의 전체 CheckBox를 누른 것과 같은 처리를 하며, 설정 값을 0으로 하면 전체 UnCheck 처리하고, 1로 하면 전체 Check 처리한다. 이외의 값을 설정하면 이전 전체 Check 설정의 반대로 처리된다.
>
> 이 속성은 Type이 DelCheck와 CheckBox인 경우 처리하며, Edit 가능한 셀의 CheckBox만 처리한다. 처리를 완료 하면 각 데이터 행 단위로 OnChange 이벤트가 발생한다.
>
> 단위데이터행 구조인 경우 Col인자에 index를 설정하면 단위데이터 첫번째 행에 대해서 처리하고, SaveName으로 설정할 경우 해당 SaveName인 행에 대해서만 처리 한다.
>
> 이 속성에 설정하는 값에 따라 CheckBox는 아래와 같이 처리된다.

|        |                             |
|:------:|:---------------------------:|
| 설정값 |            설명             |
|   0    |      전체 UnCheck하기       |
|   1    |       전체 Check 하기       |
| 그외값 | 이전 설정에 반대로 처리하기 |

- **Syntax**

|        |                                                   |
|:------:|---------------------------------------------------|
| Syntax | ObjId.**CheckAll**(Col, Value, [OnChangeEvent]) |

- **Info**

> **Return**: None

| Parameter     | Type          | 필수여부 | 설 명                               |
| ------------- | ------------- | ---- | --------------------------------- |
| Col           | Long / String | 필수   | 특정 컬럼의 Column Index 또는 SaveName   |
| Value         | Integer       | 필수   | 0 : 전체체크해제, 1 : 전체체크, 그외 : 이전값 반대 |
| OnChangeEvent | Boolean       | 선택   | OnChange 이벤트 발생 여부 Default=1      |

- **Example**

```
// 모두 선택하기
mySheet.CheckAll(1, 1);
// 모두 선택 취소하기
mySheet.CheckAll(1, 0);
```

- **제공 버전**

7.0.0.0