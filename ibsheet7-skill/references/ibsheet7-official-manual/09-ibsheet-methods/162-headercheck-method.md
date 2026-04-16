# HeaderCheck Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > HeaderCheck Method

---

- **기능**

> 헤더의 전체체크박스 값을 확인 및 설정 한다.
>
> 설정의 경우 마우스로 클릭하여 처리되는것과 달리 단순 .체크/언체크만 설정 할 수 있다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 모든행에 대해서 처리를 하고 SaveName으로 설정할 경우 해당 SaveName이 포함된 행에 대해서만 처리 한다.

- **Syntax**

|        |     |                                    |
|:------:|:---:|------------------------------------|
| Syntax | Get | ObjId.**GetHeaderCheck**(Row, Col) |

- **Info**

> **Return**: Boolean, 현재 설정 값 (Get Method 인 경우)

| Parameter | Type            | 필수여부 | 설 명                      |
| --------- | --------------- | ---- | ------------------------ |
| Row       | Number          | 필수   | 대상 행의 Index              |
| Col       | Number / String | 필수   | 대상 컬럼의 Index 또는 SaveName |

- **Example**

```javascript
// 헤더의 3번째 컬럼의 전체 체크박스 값을 확인 한다.
var CheckValue = mySheet.GetHeaderCheck(0, 3);
```

- **Syntax**

|        |     |                                           |
|:------:|:---:|-------------------------------------------|
| Syntax | Set | ObjId.**SetHeaderCheck**(Row, Col, Value) |

- **Info**

> **Return**: None

| Parameter | Type            | 필수여부 | 설 명                      |
| --------- | --------------- | ---- | ------------------------ |
| Row       | Number          | 필수   | 대상 행의 Index              |
| Col       | Number / String | 필수   | 대상 컬럼의 Index 또는 SaveName |
| Value     | Boolean         | 필수   | 체크박스에 설정하고자 하는 값         |

- **Example**

```
// 헤더의 3번째 컬럼의 전체 체크박스 값을 언체크 설정 한다..
mySheet.SetHeaderCheck(0, 3, 0);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **