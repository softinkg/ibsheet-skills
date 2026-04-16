# TabBehavior Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > TabBehavior Method

---

- **기능**

> 셀 선택 상태에서 Tab 키를 눌렀을 때의 동작 모드를 확인하거나 설정한다

True(1)로 설정시 셀의 편집 가능 여부와 상관없이 모든 셀에 대해서 탭 이동을 처리하고, false(0)로 설정시 편집 불가능한 셀을 제외하고 편집 가능한 셀에 대해서만 탭 이동을 처리 한다.

- **Syntax**

|        |     |                            |
|:------:|:---:|----------------------------|
| Syntax | Get | ObjId.**GetTabBehavior**() |

- **Info**

> **Return**: Boolean, 설정한 속성 값

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```
// Tab키의 동작을 확인한다.
mySheet.GetTabBehavior();
```

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Set | ObjId.**SetTabBehavior**(Mode) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                                |
| --------- | ------- | ---- | ---------------------------------- |
| Mode      | Boolean | 필수   | Tab key 입력시 설정할 속성 값. Default= "1" |

- **Example**

```
// 편집 가능한 셀에 대해서만 탭 이동을 설정 한다.
mySheet.SetTabBehavior(0);
```

- **제공 버전**

> **7.0.0.0**