# MousePointer Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > MousePointer Method

---

- **기능**

> 브라우져의 특성상 해당기능이 잘 동작하지 않는 경우가 많으므로 이 기능보다는 **DataLinkMouse** 기능을 사용할 것을 권한다.  
> 마우스의 모양을 설정하거나 확인한다. 설정할수 있는 값은 아래와 같다.

|         |                  |
|:-------:|:----------------:|
| 설정값  |   마우스 모양    |
| Default | 기본 화살표 모양 |
|  Hand   |   손가락 모양    |

> 이 속성은 DataLinkMouse 속성과 혼동하지 않도록 한다.

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Get | ObjId.**GetMousePointer**() |

- **Info**

> **Return**: String, 마우스 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//마우스의 모양을 확인한다.
mySheet.GetMousePointer("Default");
```

- **Syntax**

|        |     |                                    |
|:------:|:---:|------------------------------------|
| Syntax | Set | ObjId.**SetMousePointer**(Pointer) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명        |
| --------- | ------ | ---- | ---------- |
| Pointer   | String | 필수   | 설정할 마우스 모양 |

- **Example**

```javascript
function mySheet_OnMouseMove(Button, Shift, X, Y) {
//마우스 위치가 2컬럼 일때만 마우스 손가락 모양
if(mySheet.MouseCol() == 2) {
mySheet.SetMousePointer("Hand");
} else {
mySheet.SetMousePointer("Default");
}
}
```

- **제공 버전**

> **7.0.0.0  **