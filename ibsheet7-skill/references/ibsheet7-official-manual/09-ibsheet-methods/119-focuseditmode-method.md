# FocusEditMode Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > FocusEditMode Method

---

- **기능**

> 셀에 포커스가 들어갔을 때 Edit 가능한 셀은 기본적으로 단순 포커스 상태로 둘것인지 Edit 상태로 둘것인지 여부를 설정하거나 확인한다.
>
> 이 속성은 Edit 가능한 셀에 대한 Edit 모드를 설정하거나 확인한다.

| 설정값 | 내용                                            |
| --- | --------------------------------------------- |
| 0   | 포커스가 들어가면 그냥 포커스 상태 (기본값)                     |
| 1   | 포커스가 들어가면 바로 편집 상태                            |
| 2   | 컬럼타입이 Combo, ComboEdit만 포커스 상태, 나머지는 모두 편집 상태 |

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Get | ObjId.**GetFocusEditMode**() |

- **Info**

> **Return**: Integer, 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//포커스가 갔을 때 Edit 상태로 표시 할지 여부 확인
mySheet.GetFocusEditMode();
```

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Set | ObjId.**SetFocusEditMode**(Mode) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명               |
| --------- | ------- | ---- | ----------------- |
| Mode      | Integer | 필수   | 설정 여부 (Default=0) |

- **Example**

```
// 포커스가 갔을 때 Edit가 아닌 단순 포커스 상태 유지
mySheet.SetFocusEditMode(0);
//포커스가 갔을 때 Edit 상태로 표시
mySheet.SetFocusEditMode(1);
```

- **제공 버전**

7.0.0.0