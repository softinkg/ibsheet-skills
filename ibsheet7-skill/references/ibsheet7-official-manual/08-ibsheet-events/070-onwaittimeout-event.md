# OnWaitTimeOut Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnWaitTimeOut Event

---

- **기능**

> 서버에 연결하여 처리 중 일정 시간을 초과하여 처리가 중단 된 경우 이벤트가 발생한다.
>
> 아이비시트는 조회,저장과 같은 ajax 통신시 기본적으로 60초간 대기 후 커넥션을 끊으며, 이 시간은 WaitTimeOut() 메서드를 통해 조절이 가능하다.

- **Syntax**

|        |                                                |
|:------:|------------------------------------------------|
| Syntax | **function 오브젝트ID_OnWaitTimeOut**(Sec) { } |

- **Parameters**

|           |      |                                |
|:---------:|:----:|:------------------------------:|
| Parameter | Type |             설 명              |
|    Sec    | Long | 타임아웃에 걸린 시간 (단위:초) |

- **Example**

```javascript
function mySheet_OnWaitTimeOut(Sec) {
// 시간 초과가 발생한 경우
alert("대기 시간을 초과 하였습니다. ");
}
```

- **제공 버전**

7.0.0.0