# SetEndEdit Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SetEndEdit Method

---

- **기능**

> 셀 편집을 종료 한다. 편집중인 내용을 저장하고 종료하는 경우에는 Save 인자를 1(true)로 설정하고 취소하고 종료하는 경우에는 Save 인자를 0(false)로 설정한다.

- **Syntax**

|        |                            |
|:------:|----------------------------|
| Syntax | ObjId.**SetEndEdit**(Save) |

- **Info**

> **Return**: Boolean, 종료 성공 여부

| Parameter | Type    | 필수여부 | 설 명           |     |
| --------- | ------- | ---- | ------------- | --- |
| Save      | Boolean | 필수   | 편집중인 내용 저장 여부 |     |

- **Example**

```javascript
// 저장 관련 로직 처리 함수
var result = mySheet.SetEndEdit(1);
if (!result) {
return;
}
// 저장 처리 로직 진행
```

- **제공 버전**

7.0.0.0