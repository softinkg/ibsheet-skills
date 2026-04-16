# AllowCheck Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > AllowCheck Method

---

- **기능**

> 사용자가 체크박스의 값 변경시, 값의 변경을 수용할 지의 여부를 설정하거나 확인한다.
>
> OnBeforeCheck Event 발생시 AllowCheck 메소드를 통하여 체크박스의 체크 허용 / 불허의 제어가 가능하다.

- **Syntax**

|        |     |                           |
|:------:|:---:|---------------------------|
| Syntax | Get | ObjId.**GetAllowCheck**() |

- **Info**

> **Return**: Boolean, 설정된 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 체크박스의 값을 확인한다.
mySheet.GetAllowCheck();
```

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Set | ObjId.**SetAllowCheck**(Val) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                   |
| --------- | ------- | ---- | --------------------- |
| Val       | Boolean | 필수   | 값의 변경 수용여부. Default=1 |

- **Example**

```
// 체크박스의 값의 변경을 하지 않는다.
mySheet.SetAllowCheck(false);
```

- **제공 버전**

> **7.0.0.0**