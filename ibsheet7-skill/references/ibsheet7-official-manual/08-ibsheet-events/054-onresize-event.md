# ### OnResize Event

> **IBSheet7 개발자 가이드** > IBSheet Events > ### OnResize Event

---

- **기능**

> 너비를 %로 설정시, IBSheet의 너비 또는 높이가 변경된 경우 이벤트가 발생한다.
>
> 이 이벤트는 사용자가 드레그를 통해 창의 사이즈를 조절하는 경우 굉장히 빈번하게 발생하여 브라우져에 부담을 줄수 있다. 따라서 가급적이면 이 이벤트보다는 OnSmartEvent를 사용할 것을 권장한다.

- **Syntax**

|        |                                                     |
|:------:|-----------------------------------------------------|
| Syntax | **function 오브젝트ID_OnResize**(Width, Height) { } |

- **Parameters**

|           |         |           |
|:---------:|:-------:|:---------:|
| Parameter |  Type   |   설 명   |
|   Width   | Integer | 전체 너비 |
|  Height   | Integer | 전체 높이 |

- **Example**

```javascript
function mySheet_OnResize(Width, Height) {
//변경된 정보에 따라 컬럼들의 너비를 재조정한다.
mySheet.FitColWidth();
}
```

- **제공 버전**

7.0.0.0