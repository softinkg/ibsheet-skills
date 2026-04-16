# ComboOpenMode Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ComboOpenMode Method

---

- **기능**

> Combo, ComboEdit 컬럼을 한번 클릭으로 펼쳐줄지에 대해 확인하거나 설정한다.

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Get | ObjId.**GetComboOpenMode**() |

- **Info**

> **Return**: Boolean, 현재 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//ComboOpenMode 설정되어 있는 값을 확인한다.
mySheet.GetComboOpenMode();
```

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Set | ObjId.**SetComboOpenMode**(mode) |

- **Info**

> **Return**: None

| Parameter | Type             | 필수여부 | 설 명         |                                          |
| --------- | ---------------- | ---- | ----------- | ---------------------------------------- |
| mode      | Boolean          | 필수   | 0 (Default) | 콤보를 한번 클릭하면 펼쳐지지 않고 포커스만 얻는다.( Default ) |
| 1         | 콤보를 한번 클릭으로 펼친다. |      |             |                                          |

- **Example**

```
//콤보를 한번 클릭으로 연다.
Mysheet.SetComboOpenMode(1);
```

- **제공 버전**

**7.0.0.0**