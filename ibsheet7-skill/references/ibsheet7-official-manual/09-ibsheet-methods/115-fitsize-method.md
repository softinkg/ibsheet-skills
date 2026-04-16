# FitSize Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > FitSize Method

---

- **기능**

> 모든 행의 높이와 모든 컬럼의 너비를 재조정한다.
>
> RowHeight 인자가 1인 경우 모든 행의 높이를 데이터의 높이에 맞게 재조정하고, ColumnWidth 인자가 1인 경우 모든 컬럼의 너비를 컬럼 내의 가장 넓은 글자의 너비에 맞게 재조정한다.

- **Syntax**

|        |                                           |
|:------:|-------------------------------------------|
| Syntax | ObjId.**FitSize**(RowHeight, ColumnWidth) |

- **Info**

> **Return**: None

| Parameter   | Type    | 필수여부 | 설 명         |
| ----------- | ------- | ---- | ----------- |
| RowHeight   | Boolean | 필수   | 행 높이 변경 여부  |
| ColumnWidth | Boolean | 필수   | 컬럼 너비 변경 여부 |

- **Example**

```
//행 높이만 재조정하기
mySheet.FitSize(1, 0);
//컬럼 너비만 재조정하기
mySheet.FitSize(0, 1);
//모두 재조정하기
mySheet.FitSize(1, 1);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **