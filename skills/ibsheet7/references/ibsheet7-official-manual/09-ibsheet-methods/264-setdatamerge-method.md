# SetDataMerge Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SetDataMerge Method

---

- **기능**

> 데이터 영역에 대해서 셀 병합 처리를 한다..

- **Syntax**

|        |                          |
|:------:|--------------------------|
| Syntax | ObjId.**SetDataMerge**() |

- **Info**

> **Return**: (없음)

| Parameter | Type    | 필수여부 | 설 명              |
| --------- | ------- | ---- | ---------------- |
| force     | boolean | 선택   | 기존 병합 정보를 지울지 여부 |

- **Example**

```
//기존 병합 정보를 유지.
mySheet.SetDataMerge(0);
```

- **제공 버전**

| **7.0.1.0** |     |
|-------------|-----|