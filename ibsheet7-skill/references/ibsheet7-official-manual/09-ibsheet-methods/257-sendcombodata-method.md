# SendComboData Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SendComboData Method

---

- **기능**

> 데이터 타입이 Combo일때 서버로 전송되는 데이터를 설정하거나 확인한다.
>
> 컬럼에 대해서 저장 메서드를 통하여 데이터가 서버로 전달될 때, 콤보에 설정했던 Code가 전달된다. 하지만 이 메서드를 사용하면 Code 대신에 눈에 보이는 Text를 전달하거나 Code와 Text를 동시에 전달할 수도 있다.

- **Syntax**

|        |     |                                          |
|:------:|:---:|------------------------------------------|
| Syntax | Get | ObjId.**GetSendComboData**(DataRow, Col) |

- **Info**

> **Return**: String, 현재 선택된 콤보 컬럼의 전송될 데이터 형식 (Get Method 인 경우)

| Parameter | Type            | 필수여부 | 설 명                      |
| --------- | --------------- | ---- | ------------------------ |
| DataRow   | Number          | 필수   | 단위 데이터 행 Index           |
| Col       | Number / String | 필수   | 대상 컬럼의 Index 또는 SaveName |

- **Example**

```
//3컬럼에 대해서 저장시 콤보 전송 형식을 알아온다.
mySheet.GetSendComboData(0,3);
```

- **Syntax**

|        |     |                                                |
|:------:|:---:|------------------------------------------------|
| Syntax | Set | ObjId.**SetSendComboData**(DataRow, Col, Type) |

- **Info**

> **Return**: String, 현재 선택된 콤보 컬럼의 전송될 데이터 형식 (Get Method 인 경우)

| Parameter | Type          | 필수여부 | 설 명                                            |
| --------- | ------------- | ---- | ---------------------------------------------- |
| DataRow   | Long          | 필수   | 단위 데이터 행 Index                                 |
| Col       | Long / String | 필수   | 특정 컬럼의 Column Index 또는 SaveName                |
| Type      | String        | 선택   | 서버 전송 옵션 설정 ("text" 또는 "code"), Default="code" |

- **Example**

```
//3컬럼에 대해서 저장시 Code 와 Text 값이 같이 전달되도록 한다.
mySheet.SetSendComboData(0,3,"code|text");
//Dept 컬럼에 대해서 저장시 Code 대신 Text 값이 전달되도록 한다.
mySheet.SendComboData(0,"Dept","text");
```

- **제공 버전**

> **7.0.0.0**
>
> **  **