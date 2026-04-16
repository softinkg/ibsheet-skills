# MoveColumnFail Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > MoveColumnFail Method

---

- **기능**

> OnBeforeColumnMove 이벤트 안에서 사용하는 속성이며, 컬럼이동 실패 여부를 설정한다. OnBeforeColumnMove 이벤트 안에서 이 속성을 1로 설정하면 컬럼 이동은 실패하고, OnAfterColumnMove 이벤트는 발생하지 않는다.

- **Syntax**

|        |                                |
|:------:|--------------------------------|
| Syntax | ObjId.**MoveColumnFail**(Flag) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명      |
| --------- | ------- | ---- | -------- |
| Flag      | Boolean | 필수   | 컬럼이동실패여부 |

- **Example**

```javascript
//0컬럼이 3컬럼 이후의 위치로 이동하고자 할때 컬럼 이동을 취소한다
function mySheet_OnBeforeColumnMove(Col, NewPos) {
if(Col==0 && NewPos > 3) {
mySheet.MoveColumnFail(1);
}else{
mySheet.MoveColumnFail(0);
}
}
```

- **제공 버전**

> **7.0.0.0  **