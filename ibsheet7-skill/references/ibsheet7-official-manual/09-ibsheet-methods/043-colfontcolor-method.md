# ColFontColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ColFontColor Method

---

- **기능**

> 대상 컬럼 전체의 글자색을 설정하거나 확인한다. 헤더 행을 제외한 데이터 행의 글자색만 처리한다.
>
> 컬럼이 존재하지 않는 경우 에러메시지 없이 글자색 설정은 취소된다.
>
> 색상 설정은 WebColor로 설정한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 모든행에 대해서 처리를 하고 SaveName으로 설정할 경우 해당 SaveName이 포함된 행에 대해서만 처리 한다.

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Get | ObjId.**GetColFontColor**(Col) |

- **Info**

> **Return**: String, 설정된 색상값 (Get Method 인 경우)

| Parameter | Type         | 필수여부 | 설 명                             |
| --------- | ------------ | ---- | ------------------------------- |
| Col       | Long /String | 필수   | 특정 컬럼의 Column Index 또는 SaveName |

- **Example**

```
//2컬럼 글자색을 확인한다..
alert(mySheet.GetColFontColor(2));
```

- **Syntax**

|        |     |                                       |
|:------:|:---:|---------------------------------------|
| Syntax | Set | ObjId.**SetColFontColor**(Col, Color) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                             |
| --------- | ------------ | ---- | ------------------------------- |
| Col       | Long /String | 필수   | 특정 컬럼의 Column Index 또는 SaveName |
| Color     | String       | 필수   | 색상 값                            |

- **Example**

```
//컬럼 글자색을 회색으로 설정한다.
mySheet.SetColFontColor(1, "#FF0000");
//2컬럼 글자색을 1컬럼 글자색으로 설정한다.
mySheet. SetColFontColor(2, mySheet.GetColFontColor(1));
```

- **제공 버전**

7.0.0.0