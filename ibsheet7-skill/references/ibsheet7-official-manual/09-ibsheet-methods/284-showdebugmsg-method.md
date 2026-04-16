# ShowDebugMsg Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ShowDebugMsg Method

---

- **기능**

> 디버깅용 메시지의 표시여부를 확인하거나 설정한다.
>
> 디버깅 메시지를 표시하도록 설정하면 시스템 팝업 메시지로 디버깅을 위한 메시지를 표시하고, 표시 불가로 설정하면 OnDebugMsg 이벤트가 발생하여 이벤트의 인자를 통해 메시지를 확인할 수 있다.
>
> 설정값은 다음과 같다.

|      |                         |
|:----:|-------------------------|
| 종류 | 설명                    |
|  -1  | 시스템 팝업 디버그 시작 |
|  0   | 모든 디버그 종료        |

- **Syntax**

|        |                             |
|:------:|-----------------------------|
| Syntax | ObjId.**ShowDebugMsg**(Msg) |

- **Info**

> **Return**: Boolean, 디버깅용 메시지 표시 여부

| Parameter | Type    | 필수여부 | 설 명                          |
| --------- | ------- | ---- | ---------------------------- |
| Msg       | Integer | 필수   | 디버깅용 메시지 표시여부 설정 (Default=0) |

- **Example**

```javascript
//저장 처리 과정을 디버깅 메시지를 팝업으로 표시
mySheet.ShowDebugMsg(-1);
//조회
mySheet.DoSearch("list.xml");
```

- **제공 버전**

7.0.0.0