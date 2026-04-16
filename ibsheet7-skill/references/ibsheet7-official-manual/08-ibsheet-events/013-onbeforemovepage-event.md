# OnBeforeMovePage Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnBeforeMovePage Event

---

- **기능**

> 페이지 인덱스 방식의 조회모드인 경우 페이지 네비게이션 또는 페이지 이동 메소드를 통해 페이지를 이동하는 경우 이동 전에 이벤트가 발생 한다.
>
> 해당 이벤트의 반환값을 false로 설정한 경우 페이지 이동이 취소 된다.

- **Syntax**

|        |                                                             |
|:------:|-------------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnBeforeMovePage**(Current, Move) { } |

- **Parameters**

|           |        |                                  |
|:---------:|:------:|:--------------------------------:|
| Parameter |  Type  |              설 명               |
|  Current  | Number | 페이지 이동전의 현재 페이지 번호 |
|   Move    | Number |        이동할 페이지 번호        |

- **Example**

```javascript
function mySheet_OnBeforeMovePage(current, move) {
// 트랜잭션이 발생한 경우 페이지 이동을 취소 한다.
If (mySheet.IsDataModified()) {
return false;
}
}
```

- **제공 버전**

7.0.0.0