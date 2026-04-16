# GetSheetHtml Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetSheetHtml Method

---

- **기능**

> 현재 시트의 Html 소스를 반환한다.
>
> 시트에 적용된 스타일을 문자열로 가진 style과 html 소스를 문자열로 가진 body를 객체로 반환한다.
>
> \* 현재 화면에 보여지는 시트 상태 그대로의 html 코드를 리턴하므로 히든 설정 및 컬럼 사이즈 등이 동일하게 출력되며, 화면에 로드 되지 않은 자료는 출력되지 않습니다.

- **Syntax**

|        |                          |
|:------:|--------------------------|
| Syntax | ObjId.**GetSheetHtml**() |

- **Info**

> **Return**: Object, (style, body 로 이루어진 객체)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```javascript
// 시트 Html 가져오기
var code = mySheet.GetSheetHtml();

document.getElementById("styleText").value = code.style;

document.getElementById("htmlText").value += code.body;
```

- **제공 버전**

> **7.0.0.0**
>
> **  **