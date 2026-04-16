# OnColumnSort Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnColumnSort Event

---

- **기능**

> ColumnSort 함수를 실행했을 때 콜백 함수로서 호출된다.

- **Syntax**

|        |                                                      |
|:------:|------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnColumnSort**(Col, Order) { } |

- **Parameters**

| Parameter | Type           | 설 명                                           |
| --------- | -------------- | --------------------------------------------- |
| Col       | Number/ String | 소트가 처리된 컬럼 인덱스 SortEventMode 가 1인 경우 "\|"로 구분 |
| Order     | String         | 소트 방향 문자열 SortEventMode 가 1인 경우 "\|"로 구분      |

- **Example**

```javascript
function mySheet_OnColumnSort(Col, Order) {
//ColumnSort 함수를 실행되었을 때 콜백 함수로 호출되어 실행.
if(order =="ASC")
alert(col + "번째 컬럼이 오름차순으로 정렬되었습니다.");
else
alert(col + "번째 컬럼이 내림차순으로 정렬되었습니다.");
}
```

- **제공 버전**

7.0.13.106