# EnterBehavior Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > EnterBehavior Method

---

- **기능**

> 셀에서 포커스를 두고 TAB키를 누르면 옆셀로 포커스가 이동하고, Enter 키를 누르면 Edit를 시작한다. 이런 Enter의 기능을 다른 기능으로 사용할 때 이 속성을 설정한다.
>
> 기본적으로 Edit를 시작하지만 Enter를 눌렀을 때 TAB키를 누른 것 처럼 포커스를 이동하고자 한다면 이 속성을 "tab"이라고 설정한다

|        |                               |
|:------:|:-----------------------------:|
|   값   |             설명              |
| "tab"  | 탭을 누른 것 처럼 옆셀로 이동 |
| "edit" |     Edit를 시작 (Default)     |
| "down" |        아래로 내려간다        |
| "none" |     아무런 동작 하지 않음     |

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Get | ObjId.**GetEnterBehavior**() |

- **Info**

> **Return**: String, 설정한 속성 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//설정을 확인하다.
mySheet.GetEnterBehavior();
```

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Set | ObjId.**SetEnterBehavior**(Mode) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                                   |
| --------- | ------ | ---- | ------------------------------------- |
| Mode      | String | 필수   | Enter key 입력시 설정할 속성 값 Default="edit" |

- **Example**

```
//Enter를 누르면 무조건 옆으로 이동하게 한다.
mySheet.SetEnterBehavior("tab");
```

- **제공 버전**

> **7.0.0.0**
>
> **  **