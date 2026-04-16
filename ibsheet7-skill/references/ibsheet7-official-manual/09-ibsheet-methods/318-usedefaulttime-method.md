# UseDefaultTime Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > UseDefaultTime Method

---

- **기능**

> Format이 "Hms", "Hm" 인 경우 셀의 값이 공백인 상태에서 편집을 처음 시작하고자 할때 기본적으로 시스템 현재시간을 표시한다. 이 속성을 0으로 설정하면 시스템 현재 시간을 표시하지 않고 공백상태로 표시한다. 이 속성의 기본값은 1이다

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Get | ObjId.**GetUseDefaultTime**() |

- **Info**

> **Return**: Boolean, 현재 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//현재 시간을 표시 설정 확인
mySheet.GetUseDefaultTime();
```

- **Syntax**

|        |     |                                    |
|:------:|:---:|------------------------------------|
| Syntax | Set | ObjId.**SetUseDefaultTime**(Value) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                    |
| --------- | ------- | ---- | ---------------------- |
| Value     | Boolean | 필수   | 현재시간 표시 유무 (Default=1) |

- **Example**

```
//현재 시간을 표시하지 않도록 설정
mySheet.SetUseDefaultTime(0);
```

- **제공 버전**

> **7.0.0.0**