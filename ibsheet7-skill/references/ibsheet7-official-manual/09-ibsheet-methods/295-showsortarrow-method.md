# ShowSortArrow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ShowSortArrow Method

---

- **기능**

> 헤더를 눌러 소트를 할 때 소트되는 방향을 화살표 이미지로 표시할지 여부를 설정하거나 확인한다.

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Get | ObjId.**GetShowSortArrow**() |

- **Info**

> **Return**: Boolean, 화살표 이미지 표시여부(Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 설정되어 있는 소트 방향 표시여부를 확인한다.
Alert(mySheet.GetShowSortArrow());
```

- **Syntax**

|        |     |                                   |
|:------:|:---:|-----------------------------------|
| Syntax | Set | ObjId.**SetShowSortArrow**(Arrow) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명       |
| --------- | ------- | ---- | --------- |
| Arrow     | Boolean | 필수   | 화살표 표시 여부 |

- **Example**

```
// 소트 방향을 표시한다.
mySheet.SetShowSortArrow(1);
```

- **제공 버전**

> **7.0.0.0**