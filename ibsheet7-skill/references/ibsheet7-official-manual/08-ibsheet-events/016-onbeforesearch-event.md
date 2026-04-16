# OnBeforeSearch Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnBeforeSearch Event

---

- **기능**

> 조회 메소드 호출 시 Ajax 통신 직전에 발생한다

- **Syntax**

|        |                                              |
|:------:|----------------------------------------------|
| Syntax | **function 오브젝트ID_OnBeforeSearch**() { } |

- **Parameters**

| Parameter | Type | 설 명 |
| --------- | ---- | --- |
| 없음        |      |     |

- **Remarks**

> DoSearch, DoSearchChild, DoSearchPaging, DoRowSearch 메소드 호출 시 Ajax 통신 전에 발생한다.  
> 조회 중 이미지 등을 사용자가 원하는 이미지로 변경하고자 할때 사용한다.

- **Example**

```javascript
function mySheet_OnBeforeSearch() {
alert("조회중입니다.");
}
```

- **제공 버전**

7.0.0.0