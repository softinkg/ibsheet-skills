# AllowEvent4CheckAll Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > AllowEvent4CheckAll Method

---

- **기능**

> 전체선택 기능을 실행할 때 OnChange Event를 실행할지 여부를 지정한다. Data의 Row가 많은 경우 전체선택 기능을 실행하면 각 체크박스에서 OnChange Event가 발생하게 되어 속도가 저하되는 현상이 발생한다. 각 체크박스에서 OnChange 이벤트가 필요 없을 때 AllowEvent4CheckAll(0)으로 설정하면 전체선택 속도를 증가시킬 수 있다.

- **Syntax**

|        |                                    |
|:------:|------------------------------------|
| Syntax | ObjId.**AllowEvent4CheckAll**(Val) |

- **Info**

> **Return**: None.

| Parameter | Type    | 필수여부 | 설 명                           |
| --------- | ------- | ---- | ----------------------------- |
| Val       | Boolean | 필수   | OnChange Event 발생여부 Default=1 |

- **Example**

```
// 전체선택시 이벤트 발생안함
sheetObj.AllowEvent4CheckAll(0);
```

- **제공 버전**

> **7.0.0.0**