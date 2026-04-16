# SetBlur Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SetBlur Method

---

- **기능**

> 시트에 포커스를 뺀다.
>
> 시트 위에 div 레이어 형태의 팝업을 띄울 경우, tab키를 누르거나 마우스휠로 스크롤시 레이어 팝업 아래 시트 객체에 Active 되게 된다.
>
> 이때 이 함수를 이용하여 강제로 Focus를 제거 한다.

- **Syntax**

|        |                                |
|:------:|--------------------------------|
| Syntax | ObjId.**SetBlur**(clearActive) |

- **Info**

> **Return**: None

| Parameter   | Type    | 필수여부 | 설 명                                           |
| ----------- | ------- | ---- | --------------------------------------------- |
| clearActive | Boolean | 선택   | 현재 마우스 커서가 hover된 시트에 대한 정보도 지운다. Default : 0 |

- **Example**

```
// 시트에서 포커스를 뺀다.
mySheet.SetBlur(1);
```

- **제공 버전**

> **7.0.0.0**
>
> **7.0.13.157** clearActive인자 추가
>
> **  **