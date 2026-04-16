# OnDebugMsg Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnDebugMsg Event

---

- **기능**

> 모든 기능 처리 과정 중 발생하는 디버깅용 메시지가 있을 때 이벤트가 발생한다.
>
> ShowDebugMsg 속성을 0으로 설정하는 경우 디버깅용 메시지가 이 이벤트를 통해서 호출되고, -1로 설정하는 경우 사용자가 볼 수 있도록 메시지 팝업 형태로 표시된다.

- **Syntax**

|        |                                             |
|:------:|---------------------------------------------|
| Syntax | **function 오브젝트ID_OnDebugMsg**(Msg) { } |

- **Parameters**

|           |        |               |
|:---------:|:------:|:-------------:|
| Parameter |  Type  |     설 명     |
|    Msg    | String | 디버그 메시지 |

- **Example**

```javascript
function mySheet_OnDebugMsg(Msg) {
txtErr.value = txtErr.value + « \n>>>> » + Msg ;
}
//디버그 메시지 표시를 위한 TextArea 생성
<textarea name="txtErr" rows=10 cols=70></textarea>
```

- **제공 버전**

7.0.0.0