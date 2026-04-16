# OnLoad Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnLoad Event

---

- **기능**

> createIBSheet 또는 Reset 메소드 호출시 시트의 객체가 생성 완료시점에 이 이벤트가 발생 한다.
>
> 이 이벤트는 body의 onload 이전에 발생하며 DOM 엘리먼트 생성이전 시점이기 때문에 시트 객체의 메소드 확장 또는 재정의 목적으로 사용하여야 하며 초기화는 이 이벤트내에서 처리가 불가능 하다. (body 의 onload 이후 시점에서만 가능)

- **Syntax**

|        |                                      |
|:------:|--------------------------------------|
| Syntax | **function 오브젝트ID_OnLoad**() { } |

- **Parameters**

| Parameter | Type | 설 명 |
| --------- | ---- | --- |
| 없음        |      |     |

- **Example**

```javascript
function mySheet_OnLoad() {
// 시트 객체에 CusomMethod 메소드를 추가
mySheet.CustomMethod = function(arg1, arg2) {
}
}
```

- **제공 버전**

| **7.0.3.0** |     |
|-------------|-----|