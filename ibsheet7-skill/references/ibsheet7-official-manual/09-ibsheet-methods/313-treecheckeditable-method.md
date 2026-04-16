# TreeCheckEditable Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > TreeCheckEditable Method

---

- **기능**

> 트리구조의 시트에서 트리 기준 컬럼에 대한 체크박스 사용 모드인 경우 해당 컬럼의 모든 체크박스의 편집가능 여부를 확인하거나 설정한다.
>
> Get 메소드의 반환값은 Set 메소드의 설정값을 기준으로 처리 한다.
>
> 행 단위의 편집가능 여부 설정은 TreeCheckRowEditable 메소드를 참고 한다.

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Get | ObjId.**GetTreeCheckEditable**() |

- **Info**

> **Return**: Boolean, 컬럼단위 체크박스의 편집 가능 여부

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```javascript
// 컬럼단위 체크박스의 편집 가능 여부 확인
var edit = mySheet.GetTreeEditable();
console.log("TreeCheckEditable = ", edit);
```

- **Syntax**

|        |     |                                      |
|:------:|:---:|--------------------------------------|
| Syntax | Set | ObjId.**SetTreeCheckEditable**(Edit) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명            |
| --------- | ------- | ---- | -------------- |
| Edit      | Boolean | 필수   | 체크박스의 편집 가능 여부 |

- **Example**

```
// 트리 컬럼의 체크박스에 대한 비활성화 설정.
mySheet.SetTreeCheckEditable(0);
```

- **제공 버전**

| **7.0.9.0** |     |
|-------------|-----|

> **  **