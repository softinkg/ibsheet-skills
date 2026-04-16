# AllowExpand Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > AllowExpand Method

---

- **기능**

> OnBeforeExpand 이벤트가 발생한 직후에 실제로 트리를 펼치거나 접혀지는 것을 막고싶은 경우 사용한다.
>
> AllowExpand 값은 OnBeforeExpand 이벤트가 발생할 때마다 매번 1 로 리셋된다.
>
> OnBeforeExpand 이벤트 안에서 이 속성을 0으로 지정시에만 사용자의 트리 동작을 막을 수 있다.

- **Syntax**

|        |     |                            |
|:------:|:---:|----------------------------|
| Syntax | Get | ObjId.**GetAllowExpand**() |

- **Info**

> **Return**: Boolean, 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

|                           |
|---------------------------|
| mySheet.GetAllowExpand(); |

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Set | ObjId.**SetAllowExpand**(Expand) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명        |
| --------- | ------- | ---- | ---------- |
| Expand    | Boolean | 필수   | 트리의 펼쳐짐 여부 |

- **Example**

```javascript
function mySheet_OnBeforeExpand(Row,Expand) {
if(Row == 1 && Expand == 2) {
mySheet.SetAllowExpand(0);
alert("1 행에서는 펼칠 수 있지만 접을 수 없습니다.");
}
}
```

- **제공 버전**

> **7.0.0.0**