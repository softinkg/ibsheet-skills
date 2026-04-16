# OnSmartResize Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnSmartResize Event

---

- **기능**

> 시트의 너비 또는 높이가 최초 변경 시점부터 일정간격(300ms)동안 재발생이 없는 시점에 이 이벤트가 발생한다. Resize시점에 FitColWidth등의 처리를 하는 경우 OnResize 이벤트가 아닌 이 이벤트에서 처리하는 것이 성능 개선에 도움이 된다.
>
> 이 이벤트는 전역 또는 SetConfig 메소드에서 "SmartResize" 속성을 0(false)로 설정한 경우에만 발생하며, "SmartResize" 속성을 1(true)로 설정한 경우에는 발생하지 않고, OnResize 이벤트가 위의 설명처럼 발생한다.

- **Syntax**

|        |                                                          |
|:------:|----------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnSmartResize**(Width, Height) { } |

- **Parameters**

|           |         |           |
|:---------:|:-------:|:---------:|
| Parameter |  Type   |   설 명   |
|   Width   | Integer | 전체 너비 |
|  Height   | Integer | 전체 높이 |

- **Example**

```javascript
function mySheet_OnSmartResize(Width, Height) {
//변경된 정보에 따라 컬럼들의 너비를 재조정한다.
mySheet.FitColWidth();
}
```

- **제공 버전**

7.0.0.0