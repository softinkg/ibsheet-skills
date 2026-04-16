# ColumnSort Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ColumnSort Method

---

- **기능**

> 단일 또는 다중 컬럼의 데이터를 정렬한다.
>
> 여러 개 컬럼을 정렬하는 경우 컬럼을 정렬 순서에 맞게 "\|"로 연결하여 설정하면 설정한 앞컬럼 부터 순서에 맞게 정렬한다. 기본적으로 Column Index가 작은 컬럼부터 큰 컬럼 순서로 정렬한다.
>
> 단위데이터행 정렬 시 인덱스를 설정하면 단위데이터행 첫번째 행에 대해서만 처리되며, 두번째 행 이후부터는 SaveName으로 설정하여야 한다.
>
> ColSort 인자는 값을 공백으로 설정하면 모든 컬럼이 Sort 인자에 설정된 소트 방향 순서로 소트되고, 각 컬럼별로 소트 방향을 달리 설정할 때 사용한다.

KeepColOrder 인자는 Col 인자에 설정된 컬럼이 소트되는 순서를 의미하는것으로 인자값이 0 인 경우 컬럼 인덱스 순서로 소트되고, 인자값이 1인 경우 설정된 컬럼 순서 그대로 소트된다. 이 인자의 기본값을 0 이다.

> Col 인자를 빈 값으로 설정하는 경우 기존에 처리된 컬럼 정렬을 모두 초기화 한다. (Shift + 헤더 클릭과 동일)  
> **단, 조회시 sort 정보를 초기화 하려면 RemoveAll() 함수를 사용해야 한다.  
>   
> 올바른 예)  
> mySheet. RemoveAll(); //sort 정보와 데이터 모두 삭제  
> mySheet.DoSearch("url");**
>
> 소계행이 존재할 때, 단일 컬럼에 대해 사용 가능하며 다중 컬럼 소트는 지원하지 않습니다.

- **Syntax**

|        |                                                                   |
|:------:|-------------------------------------------------------------------|
| Syntax | ObjId.**ColumnSort**(Col, [Sort], [ColSort],[KeepColOrder]) |

- **Info**

> **Return**: None

| Parameter    | Type          | 필수여부 | 설 명                                       |
| ------------ | ------------- | ---- | ----------------------------------------- |
| Col          | Long / String | 필수   | 소트할 컬럼 Index 또는 SaveName을 "\|"로 조합한 문자열   |
| Sort         | String        | 선택   | "ASC" 또는 "DESC", Default ="ASC"           |
| ColSort      | String        | 선택   | 각 컬럼의 소트 방향을 "\|"로 연결한 문자열, Default=""    |
| KeepColOrder | Boolean       | 선택   | Cols파라미터에서 지정된 순서대로 소트할 것인지 선택, Default=0 |

- **Example**

```
//기존에 설정된 ColumnSort 초기화
mySheet.ColumnSort(“”);
//6컬럼만 내림차순으로 정렬
mySheet.ColumnSort("6", "DESC")
//4컬럼을 중심으로 먼저 오름차순 정렬하고, 그 안에서 5컬럼 오름차순 정렬
mySheet.ColumnSort("4|5")
//2,3,4컬럼 순서로 정렬하고, 내림차순으로 정렬한다.
mySheet.ColumnSort("2|3|4", "DESC");
//3,2,4컬럼을 2,3,4컬럼인덱스 순서대로 내림차순, 오름차순, 오름차순으로 정렬한다.
mySheet.ColumnSort("3|2|4", "DESC","ASC|DESC|ASC");
//3,2,4컬럼을 3,2,4컬럼 지정된 순서대로 오름차순, 내림차순, 오름차순으로 정렬한다.
mySheet.ColumnSort("3|2|4", " DESC ","ASC|DESC|ASC", 1);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **