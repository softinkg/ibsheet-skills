# OnBeforeColumnMove Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnBeforeColumnMove Event

---

- **기능**

> 사용자가 마우스를 이용하여 컬럼 이동을 시작하거나 MoveColumnPos 함수를 이용하여 컬럼 이동을 시작할 때 이벤트가 발생한다. MoveColumnFail(1) 함수를 이용하여 컬럼이동을 방지할 수 있다.

- **Syntax**

|        |                                                             |
|:------:|-------------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnBeforeColumnMove**(Col, NewPos) { } |

- **Parameters**

|           |      |                          |
|:---------:|:----:|:------------------------:|
| Parameter | Type |          설 명           |
|    Col    | Long |   이동할 컬럼의 Index    |
|  NewPos   | Long | 이동될 위치의 컬럼 Index |

- **Example**

```javascript
//0컬럼이 3컬럼 이후의 위치로 이동하고자 할때 컬럼 이동을 취소한다
function mySheet_OnBeforeColumnMove(Col, NewPos) {
if(Col==0 && NewPos > 3) {
mySheet.MoveColumnFail(1);
}
}
```

- **제공 버전**

7.0.0.0