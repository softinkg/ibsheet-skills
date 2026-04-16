# FitSizeCol Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > FitSizeCol Method

---

- **기능**

> 대상 컬럼의 너비를 컬럼 내의 가장 넓은 글자의 너비에 맞게 재조정한다.
>
> 재조정의 범위는 전역속성 FitSizeColMode 설정을 따른다.

- **Syntax**

|        |                           |
|:------:|---------------------------|
| Syntax | ObjId.**FitSizeCol**(Col) |

- **Info**

> **Return**: None

| Parameter | Type           | 필수여부 | 설 명                      |
| --------- | -------------- | ---- | ------------------------ |
| Col       | Number/ String | 필수   | 대상 컬럼의 Index 또는 SaveName |

- **Example**

```
//SaveName 이 "sTarget"인 컬럼에 대한 처리
mySheet.FitSizeCol("sTarget");
```

- **제공 버전**

| **7.0.4.0** |     |
|-------------|-----|

> **  **