# OnAfterPaste Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnAfterPaste Event

---

- **기능**

> 클립보드 붙여넣기 완료 시점에 이벤트가 발생한다.

- **Syntax**

|        |                                            |
|:------:|--------------------------------------------|
| Syntax | **function 오브젝트ID_OnAfterPaste**() { } |

- **Parameters**

| Parameter | Type | 설 명 |
| --------- | ---- | --- |
| 없음        |      |     |

- **Example**

```javascript
function mySheet_OnAfterPaste() {
console.log("클립보드 붙여넣기 완료");
}
```

- **제공 버전**

| **7.0.13.21** |     |
|---------------|-----|