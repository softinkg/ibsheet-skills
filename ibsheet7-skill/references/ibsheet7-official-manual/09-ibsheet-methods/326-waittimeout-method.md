# WaitTimeOut Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > WaitTimeOut Method

---

- **기능**

> 서버에 연결하여 응답을 대기하는 시간을 확인하거나 설정한다. (단위:초).

- **Syntax**

|        |     |                            |
|:------:|:---:|----------------------------|
| Syntax | Get | ObjId.**GetWaitTimeOut**() |

- **Info**

> **Return**: Integer, 현재 설정 값(Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 서버에 연결하여 응답을 대기하는 시간을 확인
alert(mySheet.GetWaitTimeOut());
```

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Set | ObjId.**SetWaitTimeOut**(time) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                  |
| --------- | ------- | ---- | -------------------- |
| time      | Integer | 필수   | 설정할 초시간 (Default=60) |

- **Example**

```
// 서버에 연결하여 응답을 대기하는 시간을 확인하거나 설정
mySheet.SetWaitTimeOut(120);
```

- **제공 버전**

> **7.0.0.0**

**  
  **