# OnAfterColumnMove Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnAfterColumnMove Event

---

- **기능**

> 사용자가 마우스드레그를 이용하여 컬럼을 이동하거나 MoveColumnPos 함수를 이용하여 컬럼을 이동하고 이동이 성공적으로 완료되었을 때 이벤트가 발생한다.

- **Syntax**

|        |                                                            |
|:------:|------------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnAfterColumnMove**(Col, NewPos) { } |

- **Parameters**

|           |      |                          |
|:---------:|:----:|:------------------------:|
| Parameter | Type |          설 명           |
|    Col    | Long |   이동한 컬럼의 Index    |
|  NewPos   | Long | 이동된 위치의 컬럼 Index |

- **Example**

```javascript
//컬럼이 이동된 후 이벤트가 발생한다.
Function mySheet_OnAfterColumnMove(Col, NewPos) {
alert(Col + " 위치가 " + NewPos + " 위치로 이동되었습니다..");
}
```

- **제공 버전**

7.0.0.0

- **See Also  
  [OnBeforeColumnMove](#onbeforecolumnmove-event) , [MoveColumnPos](#movecolumnpos-method) , [MoveColumnFail](#movecolumnfail-method)**