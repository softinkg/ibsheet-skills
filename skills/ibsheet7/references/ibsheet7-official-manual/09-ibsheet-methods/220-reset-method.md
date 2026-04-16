# Reset Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > Reset Method

---

- **기능**

> IBSheet에 설정된 모든 기본 속성을 제거하고 초기상태로 변경한다.

- **Syntax**

|        |                                |
|:------:|--------------------------------|
| Syntax | ObjId.**Reset**([KeepTheme]) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                         |
| --------- | ------- | ---- | --------------------------- |
| KeepTheme | Boolean | 선택   | 적용되어 있는 테마 유지 여부, Default=0 |

- **Example**

```
//초기 상태로 변경하기
mySheet.Reset();
```

- **제공 버전**

> **7.0.0.0**
>
> **  **