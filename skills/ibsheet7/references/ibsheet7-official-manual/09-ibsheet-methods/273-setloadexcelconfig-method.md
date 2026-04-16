# SetLoadExcelConfig Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SetLoadExcelConfig Method

---

- **기능**

> LoadExcel 메소드의 기본 속성을 정의 한다. 이 메소드를 통해 정의한 속성은 LoadExcel 메소드의 기본값으로 처리가 된다.

- **Syntax**

|        |                                       |
|:------:|---------------------------------------|
| Syntax | ObjId.**SetLoadExcelConfig**([Opt]) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명 |                                    |
| --------- | ------ | ---- | --- | ---------------------------------- |
| Opt       | Object | 선택   |     | 기본으로 정의할 속성 객체 세부 사항은 LoadExcel 참고 |

- **Example**

```
// MaxFileSize, FileExt 속성에 대한 기본값 정의
mySheet.SetLoadExcelConfig({
"FileExt": "xlsx",
"MaxFileSize": 10
});
```

- **제공 버전**

| **7.0.13.27** |     |
|---------------|-----|