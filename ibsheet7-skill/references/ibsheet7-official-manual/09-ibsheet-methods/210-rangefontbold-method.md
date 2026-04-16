# RangeFontBold Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RangeFontBold Method

---

- **기능**

> 셀의 범위 영역의 글자볼드 여부를 설정 한다.
>
> 그 영역이 데이터 영역이든 헤더 영역이든 셀의 글자볼드를 설정할 수 있으며, 영역이 헤더와 데이터 영역을 벗어나는 경우 에러메시지 없이 글자볼드 설정은 취소 된다.

- **Syntax**

|        |     |                                                       |
|:------:|:---:|-------------------------------------------------------|
| Syntax | Set | ObjId.**RangeFontBold**(Row1, Col1, Row2, Col2, Bold) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                   |
| --------- | ------- | ---- | --------------------- |
| Row1      | Number  | 필수   | 범위 시작 셀의 Row Index    |
| Col1      | Number  | 필수   | 범위 시작 셀의 Column Index |
| Row2      | Number  | 필수   | 범위 종료 셀의 Row Index    |
| Col2      | Number  | 필수   | 범위 종료 셀의 Column Index |
| Bold      | Boolean | 필수   | 볼드 설정 여부              |

- **Example**

```
//영역 글자 볼드 설정하기
mySheet.RangeFontBold(1, 0, 2, 2, 1);
```

- **제공 버전**

| **7.0.13.16** |     |
|---------------|-----|

> **  **