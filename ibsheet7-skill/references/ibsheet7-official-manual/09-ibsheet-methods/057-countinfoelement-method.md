# CountInfoElement Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CountInfoElement Method

---

- **기능**

> 건수 정보를 시트 외부의 DOM 엘리먼트에 표현하기 위한 설정을 하거나 설정된 엘리먼트를 확인 한다.
>
> 설정이 가능한 DOM 엘리먼트는 input 과 div, span 등의 innerText 를 지원하는 DOM 엘리먼트이다.

- **Syntax**

|        |     |                                 |
|:------:|:---:|---------------------------------|
| Syntax | Get | ObjId.**GetCountInfoElement**() |

- **Info**

> **Return**: object, 설정된 DOM 엘리먼트 객체

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```javascript
// 건수정보를 표시할 DOM 엘리먼트 객체를 확인 한다.
var elem = mySheet.GetCountInfoElement();
```

- **Syntax**

|        |     |                                        |
|:------:|:---:|----------------------------------------|
| Syntax | Set | ObjId.**SetCountInfoElement**(Element) |

- **Info**

> **Return**: None

| Parameter | Type           | 필수여부 | 설 명                   |
| --------- | -------------- | ---- | --------------------- |
| Element   | Object/ String | 필수   | 설정할 DOM 엘리먼트 객체 또는 Id |

- **Example**

```
// 건수정보를 표시할 DOM 엘리먼트를 설정한다.
// ("countElem" 아이디의 DOM 엘리먼트가 생성되어 있어야 함)
mySheet.SetCountInfoElement("countElem");
}
```

- **제공 버전**

> **7.0.0.0**
>
> **  **