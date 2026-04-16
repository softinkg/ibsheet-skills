# CreateUniteTable Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CreateUniteTable Method

---

- **기능**

> UserChildGrid 사용시에 부모 그리드와 자식 그리드의 컬럼정보가 합쳐진 그리드를 생성한다.
>
> 단, 두 그리드의 초기화 정보의 SaveName은 중복되지 않아야한다.
>
> 헤더의 줄 수도 동일하여야 한다.
>
> 기타 전체 속성 부분 및 일부 공통 속성은 그리드 초기값으로 생성된다.

- **Syntax**

|        |     |                                     |
|:------:|:---:|-------------------------------------|
| Syntax | Get | ObjId.**CreateUniteTable**(sheetid) |

- **Info**

> **Return**: (없음)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//mySheet2에 mySheet와 ChildGrid의 정보를 취합하여 그리드를 생성한다.
mySheet.CreateUniteTable(mysheet2);
```

- **제공 버전**

7.0.13.78