# ColFontUnderline Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ColFontUnderline Method

---

- **기능**

> 대상 컬럼 전체의 글자 언더라인을 설정하거나 확인한다. 헤더 행을 제외한 데이터 행만 처리한다.
>
> 컬럼이 존재하지 않는 경우 에러메시지 없이 언더라인 설정은 취소된다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 모든행에 대해서 처리를 하고 SaveName으로 설정할 경우 해당 SaveName이 포함된 행에 대해서만 처리 한다.

- **Syntax**

|        |     |                                    |
|:------:|:---:|------------------------------------|
| Syntax | Get | ObjId.**GetColFontUnderline**(Col) |

- **Info**

> **Return**: Boolean, 밑줄 설정 값 (Get Method 인 경우)

| Parameter | Type           | 필수여부 | 설 명                      |
| --------- | -------------- | ---- | ------------------------ |
| Col       | Number /String | 필수   | 특정 컬럼의 Index 또는 SaveName |

- **Example**

```
//컬럼 전체 글자에 언더라인 설정여부를 확인한다.
Alert(mySheet.GetColFontUnderline(1));
```

- **Syntax**

|        |     |                                               |
|:------:|:---:|-----------------------------------------------|
| Syntax | Set | ObjId.**SetColFontUnderline**(Col, Underline) |

- **Info**

> **Return**: None

| Parameter | Type           | 필수여부 | 설 명                      |
| --------- | -------------- | ---- | ------------------------ |
| Col       | Number /String | 필수   | 특정 컬럼의 Index 또는 SaveName |
| Underline | Boolean        | 필수   | 밑줄 여부                    |

- **Example**

```
//컬럼 전체 글자에 언더라인을 설정한다.
mySheet.SetColFontUnderline(1, 1);
```

- **제공 버전**

7.0.0.0