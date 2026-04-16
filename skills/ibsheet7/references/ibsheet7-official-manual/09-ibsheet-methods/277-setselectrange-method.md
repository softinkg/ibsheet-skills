# SetSelectRange Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SetSelectRange Method

---

- **기능**

> 특정 셀의 범위 영역에 대해서 셀렉션 설정을 한다. 시트에서 마우스 드래그를 이용한 셀렉션 처리를 이 메소드를 통해서 동일하게 할 수 있다.
>
> 인자를 설정하지 않거나 잘못 설정한 경우 이전 시트의 셀렉션 설정은 클리어 된다. 범위 종료셀의 행 또는 컬럼 정보를 설정하지 않은 경우 범위 시작 셀의 정보로 자동 설정된다.

- **Syntax**

|        |                                                  |
|:------:|--------------------------------------------------|
| Syntax | ObjId.**SetSelectRange**(Row1, Col1, Row2, Col2) |

- **Info**

> **Return**: None

| Parameter | Type           | 필수여부 | 설 명                           |     |
| --------- | -------------- | ---- | ----------------------------- | --- |
| Row1      | Number         | 필수   | 범위 시작 셀의 행 Index              |     |
| Col1      | Number/ String | 필수   | 범위 시작 셀의 컬럼 Index 또는 SaveName |     |
| Row2      | Number         | 선택   | 범위 종료 셀의 행 Index              |     |
| Col2      | Number/ String | 선택   | 범위 종료 셀의 컬럼 Index 또는 SaveName |     |

- **Example**

```
// (2,2)부터(2,10)까지 셀렉션 처리를 한다..
mySheet.SetSelectRange(2, 2, 2, 10);
// 이전 셀렉션 처리를 클리어 한다.
mySheet.SetSelectRange();
```

- **제공 버전**

| **7.0.7.0** |     |
|-------------|-----|