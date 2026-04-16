# SetTabIndex Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SetTabIndex Method

---

- **기능**

> 시트에 TabIndex를 부여하여 tab을 통해 시트 안/밖으로 포커스가 움직일 수 있게 설정.

- **Syntax**

|        |                                 |
|:------:|---------------------------------|
| Syntax | ObjId.**SetTabIndex**(TabIndex) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명          |     |
| --------- | ------ | ---- | ------------ | --- |
| TabIndex  | Number | 필수   | 설정할 TabIndex |     |

- **Example**

```
// 시트에 tabIndex를 1로 설정한다.
mySheet.SetTabIndex (1);
```

- **제공 버전**

| **7.0.13.100** |     |
|----------------|-----|