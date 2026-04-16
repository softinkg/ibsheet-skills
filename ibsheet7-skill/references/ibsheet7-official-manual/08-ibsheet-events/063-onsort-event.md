# OnSort Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnSort Event

---

- **기능**

> 헤더를 마우스로 눌러 데이터가 소트 완료 되었을 때 이벤트가 발생한다. Col 인자는 컬럼 Index 번호이고, SortOrder는 소트 방향으로 아래와 같이 표현된다. SortEventMode 가 1로 설정되어 있으면 소트되어 있는 모든 컬럼의 정보가 "\|"로 구분하여 표현된다.
>
> 시트가 단위데이터행 구조인 경우 Col 인자는 Index 값이 아닌 해당 컬럼의 SaveName으로 설정되며 SaveName 이 설정되지 않은 경우 -1로 설정된어 이벤트가 발생 한다.

|           |          |
|:---------:|:--------:|
| SortOrder |   설명   |
|   "ASC"   | 오름차순 |
|  "DESC"   | 내림차순 |

- **Syntax**

|        |                                                    |
|:------:|----------------------------------------------------|
| Syntax | **function 오브젝트ID_OnSort**(Col, SortOrder) { } |

- **Parameters**

| Parameter | Type           | 설 명                                           |
| --------- | -------------- | --------------------------------------------- |
| Col       | Number/ String | 소트가 처리된 컬럼 인덱스 SortEventMode 가 1인 경우 "\|"로 구분 |
| SortOrder | String         | 소트 방향 문자열 SortEventMode 가 1인 경우 "\|"로 구분      |

- **Example**

```javascript
function mySheet_OnSort(col, order) {
if(order =="ASC")
alert(col + "번째 컬럼이 오름차순으로 정렬되었습니다.");
else
alert(col + "번째 컬럼이 내림차순으로 정렬되었습니다.");
}
```

- **제공 버전**

| **7.0.0.0** |                               |
|:-----------:|-------------------------------|
| **7.0.6.0** | 단위데이터행 구조에 대한 지원 |