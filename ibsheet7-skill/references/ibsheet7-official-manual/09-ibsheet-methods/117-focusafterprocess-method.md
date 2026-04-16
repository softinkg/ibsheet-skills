# FocusAfterProcess Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > FocusAfterProcess Method

---

- **기능**

> 조회 완료 후 포커스를 데이터 행으로 설정할지 여부를 확인하거나 설정한다.
>
> 기본적으로 DoSearch 함수를 이용하여 데이터 조회를 완료하면 포커스를 데이터 행의 첫행에 두도록 처리한다. 그러나 이 속성을 false로 설정하면 조회 완료하여도 기존 다른 컨트롤에 있는 포커스를 뺏어오지 않는다.

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Get | ObjId.**GetFocusAfterProcess**() |

- **Info**

> **Return**: Boolean, 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//조회 후 포커스 여부
mySheet.GetFocusAfterProcess();
```

- **Syntax**

|        |     |                                      |
|:------:|:---:|--------------------------------------|
| Syntax | Set | ObjId.**SetFocusAfterProcess**(mode) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                   |
| --------- | ------- | ---- | --------------------- |
| mode      | Boolean | 필수   | 포커스 설정 여부 (Default=1) |

- **Example**

```
//조회 후 포커스를 두지 않음
mySheet.SetFocusAfterProcess(0);
```

- **제공 버전**

7.0.0.0