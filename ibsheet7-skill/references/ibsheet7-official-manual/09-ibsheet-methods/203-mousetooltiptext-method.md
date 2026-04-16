# MouseToolTipText Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > MouseToolTipText Method

---

- **기능**

> 마우스에 표시될 풍선도움말을 확인하거나 설정한다.

- **Syntax**

|        |     |                                 |
|:------:|:---:|---------------------------------|
| Syntax | Get | ObjId.**GetMouseToolTipText**() |

- **Info**

> **Return**: String, 설정된 문자열

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```
//설정된 MouseToolTipText 값을 확인한다.
mySheet.GetMouseToolTipText();
```

- **Syntax**

|        |     |                                      |
|:------:|:---:|--------------------------------------|
| Syntax | Set | ObjId.**SetMouseToolTipText**(Value) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명     |
| --------- | ------ | ---- | ------- |
| Value     | String | 필수   | 설정할 문자열 |

- **Example**

```javascript
// MouseMove 이벤트에서 마우스 위치의 X, Y 좌표값을 ToopTip으로 설정 한다.
Function mySheet_OnMouseMove(button, shift, x, y) {
var value = "마우스 좌표 = " + x + "," + y;
mySheet.SetMouseToolTipText(value);
}.
```

- **제공 버전**

> **7.0.0.0**