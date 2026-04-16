# ColWidth Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ColWidth Method

---

- **기능**

> 특정 컬럼의 너비를 설정하거나 확인한다.
>
> 픽셀 단위의 너비를 설정할 수 있고, 값을 0으로 설정하면 해당 컬럼 내의 Text 중 가장 긴 값에 맞게 너비를 자동 조정한다.
>
> 컬럼이 존재하지 않는 경우 에러메시지는 표시하지 않지만 처리는 취소된다.

- **Syntax**

|        |     |                            |
|:------:|:---:|----------------------------|
| Syntax | Get | ObjId.**GetColWidth**(Col) |

- **Info**

> **Return**: Integer, 특정컬럼의 너비 픽셀 값 (Get Method 인 경우)

| Parameter | Type         | 필수여부 | 설 명                             |
| --------- | ------------ | ---- | ------------------------------- |
| Col       | Long/ String | 필수   | 특정 컬럼의 Column Index 또는 SaveName |

- **Example**

```
// 1컬럼의 너비값을 확인
mySheet.GetColWidth(1);
```

- **Syntax**

|        |     |                                   |
|:------:|:---:|-----------------------------------|
| Syntax | Set | ObjId.**SetColWidth**(Col, Width) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                             |
| --------- | ------------ | ---- | ------------------------------- |
| Col       | Long/ String | 필수   | 특정 컬럼의 Column Index 또는 SaveName |
| Width     | Integer      | 필수   | 너비 픽셀 값                         |

- **Example**

```
//50 픽셀로 너비 수정
mySheet.SetColWidth(1, 50);
//컬럼 내의 최대 글자 너비로 자동 변경
mySheet.SetColWidth(2, 0);
//3컬럼의 너비를 2컬럼의 너비와 동일하게 변경
mySheet.SetColWidth(3, mySheet.GetColWidth(2));
```

- **제공 버전**

7.0.0.0