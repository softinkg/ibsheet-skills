# DisposeSheet Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DisposeSheet Method

---

- **기능**

> IBSheet를 삭제하고, 사용하던 메모리를 강제로 해제한다.
>
> 설정값은 아래와 같다.

|             |       |                                    |
|:-----------:|:-----:|:----------------------------------:|
|   설정 값   | Value |               설 명                |
| removeEvent |   0   |          메모리 해제한다.          |
| removeEvent |   1   | 메모리 해제 및 이벤트를 해제 한다. |

- **Syntax**

|        |                                         |
|:------:|-----------------------------------------|
| Syntax | ObjId.**DisposeSheet**([removeEvent]) |

- **Info**

| Parameter   | Type    | 필수여부 | 설 명                              |
| ----------- | ------- | ---- | -------------------------------- |
| removeEvent | boolean | 선택   | 시트의 이벤트 리스너 삭제 여부 선택 Default = 0 |

- **Example**

```
// 생성된 mySheet 를 제거한다
mySheet.DisposeSheet();
```

- **제공 버전**

|  **7.0.0.0**  |                  |
|:-------------:|------------------|
| **7.0.13.40** | removeEvent 추가 |