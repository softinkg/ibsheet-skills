# OnBeforeSave Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnBeforeSave Event

---

- **기능**

> 저장 메소드 호출 시 Ajax 통신 직전에 발생한다

- **Syntax**

|        |                                            |
|:------:|--------------------------------------------|
| Syntax | **function 오브젝트ID_OnBeforeSave**() { } |

- **Parameters**

| Parameter | Type | 설 명 |
| --------- | ---- | --- |
| 없음        |      |     |

- **Remarks**

> DoSave, DoAllSave 메소드 호출 시 Ajax 통신 전에 발생한다.  
> 저장 중 이미지 등을 사용자가 원하는 이미지로 변경하고자 할때 사용한다.

- **Example**

```javascript
function mySheet_OnBeforeSave() {
alert("저장중입니다.");
}
```

- **제공 버전**

7.0.0.0