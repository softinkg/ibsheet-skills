# ColDelete Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ColDelete Method

---

- **기능**

> 특정 컬럼을 삭제 한다.
>
> Col 인자를 설정하지 않는 경우 마지막 컬럼을 삭제 한다.
>
> 아래과 같은 조건에 해당하는 컬럼을 삭제가 불가능 하다.

- 컬럼 타입이 Seq, Status, DelCheck 인 경우

- 타 컬럼의 계산식(CalcLogic)에 사용되는 컬럼인 경우

- 트리 기준 컬럼(TreeCol 속성 설정이 있는 컬럼)인 경우

- 단위데이터행 구조의 FixedMerge에 포함된 컬럼인 경우

<!-- -->

- **Syntax**

|        |                              |
|:------:|------------------------------|
| Syntax | ObjId.**ColDelete**([Col]) |

- **Info**

> **Return**: None

| Parameter | Type           | 필수여부 | 설 명                                         |
| --------- | -------------- | ---- | ------------------------------------------- |
| Col       | Number /String | 선택   | 대상 컬럼의 Index 또는 SaveName (Default : 마지막 컬럼) |

- **Example**

```
// Index값이 3인 컬럼을 삭제 한다.
mySheet.ColDelete(3);
// SaveName이 "sText"인 컬럼을 삭제 한다.
mySheet.ColDelete("sText");
// 마지막 컬럼을 삭제 한다.
mySheet.ColDelete();
```

- **제공 버전**

**7.0.0.0**

**  **