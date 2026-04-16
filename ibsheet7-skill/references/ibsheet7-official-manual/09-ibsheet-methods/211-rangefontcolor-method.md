# RangeFontColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RangeFontColor Method

---

- **기능**

> 셀의 범위 영역의 글자색을 설정 한다.
>
> 그 영역이 데이터 영역이든 헤더 영역이든 셀의 글자색을 설정할 수 있으며, 영역이 헤더와 데이터 영역을 벗어나는 경우 에러메시지 없이 글자색 설정은 취소 된다.

- **Syntax**

|        |     |                                                         |
|:------:|:---:|---------------------------------------------------------|
| Syntax | Set | ObjId.**RangeFontColor**(Row1, Col1, Row2, Col2, Color) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                   |
| --------- | ------ | ---- | --------------------- |
| Row1      | Number | 필수   | 범위 시작 셀의 Row Index    |
| Col1      | Number | 필수   | 범위 시작 셀의 Column Index |
| Row2      | Number | 필수   | 범위 종료 셀의 Row Index    |
| Col2      | Number | 필수   | 범위 종료 셀의 Column Index |
| Color     | String | 필수   | WebColor              |

- **Example**

```
//영역에 글자색 설정하기
mySheet.RangeFontColor(1,0,10,10, "FF0000");
```

- **제공 버전**

| **7.0.13.16** |     |
|---------------|-----|

> **  **