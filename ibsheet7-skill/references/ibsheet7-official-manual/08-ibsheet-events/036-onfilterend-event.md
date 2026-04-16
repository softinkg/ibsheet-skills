# OnFilterEnd Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnFilterEnd Event

---

- **기능**

> 필터링이 완료된 후에 이벤트가 발생한다.

- **Syntax**

|        |                                                             |
|:------:|-------------------------------------------------------------|
| Syntax | **function 오브젝트ID_ OnFilterEnd**(RowCnt, FirstRow) { } |

- **Parameters**

|           |      |                                 |
|:---------:|:----:|:-------------------------------:|
| Parameter | Type |              설 명              |
|  RowCnt   | Long |     필터링된 이후 행의 개수     |
| FirstRow  | Long | 필터링된 이후 첫번째 행의 Index |

- **Example**

```javascript
function mySheet_ OnFilterEnd(RowCnt, FirstRow) {
}
```

- **제공 버전**

7.0.0.0