# RangeBackColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RangeBackColor Method

---

- **기능**

> 셀의 범위 영역의 배경색을 설정 한다.
>
> 그 영역이 데이터 영역이든 헤더 영역이든 셀의 배경색을 설정 할 수 있으며, 영역이 헤더와 데이터 영역을 벗어나는 경우 에러메시지 없이 배경색 설정은 취소 된다.

- **Syntax**

|        |     |                                                     |
|:------:|:---:|-----------------------------------------------------|
| Syntax | Set | ObjId.**RangeBackColor**(Row1,Col1,Row2,Col2,Color) |

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
//영역에 배경색 설정하기
mySheet.RangeBackColor(1,0,10,10, "#FFFF00");
```

- **제공 버전**

| **7.0.13.16** |     |
|---------------|-----|