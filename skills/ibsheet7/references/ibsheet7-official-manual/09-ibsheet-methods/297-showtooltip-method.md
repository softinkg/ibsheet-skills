# ShowToolTip Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ShowToolTip Method

---

- **기능**

> 마우스 커서가 위치한 셀의 내용을 툴팁으로 표현한다.
>
> 이 기능은 초기화 함수인 SetConfig 의 ToolTip 인자를 이용하여 설정 할 수도 있다.
>
> 함수의 호출 시점은 초기화 이후 조회 처리전에 호출 하여야 한다.

- **Syntax**

|        |                                |
|:------:|--------------------------------|
| Syntax | ObjId.**ShowToolTip**(ToolTip) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명      |
| --------- | ------- | ---- | -------- |
| ToolTip   | Boolean | 필수   | 툴팁 표시 여부 |

- **Example**

```
//툴팁 설정
mySheet.ShowToolTip(1);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **