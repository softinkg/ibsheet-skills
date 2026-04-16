# ShowPivotDialog Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ShowPivotDialog Method

---

- **기능**

> 사용자가 시트에서 ctrl+alt+T 입력시 표시되는 피벗 테이블 설정 팝업을 호출 한다.
>
> 피벗 설정 다이얼로그를 통해 생성된 피벗 테이블 시트는 원본시트명 + "_Pivot"으로 시트명이 설정된다.

- **Syntax**

|        |                             |
|:------:|-----------------------------|
| Syntax | ObjId.**ShowPivotDialog**() |

- **Info**

> **Return**: None

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```
//피벗 테이블 설정 팝업을 호출한다.
mySheet.ShowPivotDialog();
```

- **제공 버전**

| **7.0.0.0**  |                          |
|:------------:|--------------------------|
| **7.0.13.0** | 합계 비율 선택 기능 추가 |

> **  **