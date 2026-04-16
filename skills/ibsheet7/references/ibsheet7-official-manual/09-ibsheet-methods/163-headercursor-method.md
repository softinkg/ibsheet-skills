# HeaderCursor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > HeaderCursor Method

---

- **기능**

> 헤더의 마우스 오버시 커서의 모양을 설정한다.
>
> "Default","Pointer" 로 설정이 가능하며 기본적으로 "Default"값이 설정된다.

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Get | ObjId.**GetHeaderCursor**() |

- **Info**

> **Return**: String

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 헤더의 마우스 커서포인터를 확인한다.
mySheet.GetHeaderCursor();
```

- **Syntax**

|        |     |                                   |
|:------:|:---:|-----------------------------------|
| Syntax | Set | ObjId.**SetHeaderCursor**(Cursor) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명       |
| --------- | ------ | ---- | --------- |
| Cursor    | String | 필수   | 마우스 모양 설정 |

- **Example**

```
// 헤더의 마우스 커서포인터를 손가락 모양으로 변경한다.
mySheet.SetHeaderCursor('Pointer');
```

- **제공 버전**

> **7.0.13.60  **