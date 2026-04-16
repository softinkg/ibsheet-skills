# GetColMaxValue Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetColMaxValue Method

---

- **기능**

> 해당 컬럼의 최대값을 가져온다.
>
> 단, 숫자타입(Int, Float, AutoSum)의 컬럼에서만 지원한다.

|          |               |                            |
|:--------:|:-------------:|:--------------------------:|
| Property |     Type      |           설 명            |
|   Col    | Number/String | 컬럼의 Index 또는 SaveName |

- **Syntax**

|        |                               |
|:------:|-------------------------------|
| Syntax | ObjId.**GetColMaxValue**(Col) |

- **Info**

> **Return**: Number, 해당 컬럼의 최소값

| Parameter | Type          | 필수여부 | 설 명                        |
| --------- | ------------- | ---- | -------------------------- |
| Col       | Long / String | 필수   | 특정 셀의 컬럼 Index 또는 SaveName |

- **Example**

```
// Index가 3인 컬럼의 최대값을 가져온다.
mySheet.GetColMaxValue(3);
```

- **제공 버전**

| **7.0.13.67** |     |
|---------------|-----|

> **  **