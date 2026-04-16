# GetSelectionRows Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetSelectionRows Method

---

- **기능**

> 사용자가 드레그를 통해 선택한 영역의 행을 구분자로 구분하여 반환한다.
>
> 구분자를 설정하지 않으면 기본적으로 "\|"로 묶어서 반환한다.

- **Syntax**

|        |                                          |
|:------:|------------------------------------------|
| Syntax | ObjId.**GetSelectionRows**([DeliChar]) |

- **Info**

> **Return**: String, 선택되어있는 행번 조합 문자열

| Parameter | Type   | 필수여부 | 설 명                 |
| --------- | ------ | ---- | ------------------- |
| DeliChar  | String | 선택   | 조합구분자, Default="\|" |

- **Example**

```javascript
//"/" 구분자로 연결하여 선택된 행번 가져오기
var sRowStr = mySheet.GetSelectionRows("/");
//자바 스크립트 배열로 만들기
var arr = sRowStr.split("/");
for (i=0; i<arr.length(); i++) {
alert(arr[i] + " 행이 선택되었음");
}
```

- **제공 버전**

> **7.0.0.0**
>
> **  **