# ColHidden Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ColHidden Method

---

- **기능**

> 컬럼의 숨김여부를 설정하거나 확인한다.

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Get | ObjId.**GetColHidden**(Col) |

- **Info**

> **Return**: Boolean, 숨김 설정 값 (Get Method 인 경우)

| Parameter | Type           | 필수여부 | 설 명                      |
| --------- | -------------- | ---- | ------------------------ |
| Col       | number /string | 필수   | 특정 컬럼의 Index 또는 SaveName |

- **Example**

```javascript
//해당 컬럼이 숨겨졌는지 확인한다.
var isHide = mySheet.GetColHidden(12);
var isHide2 = mySheet.GetColHidden("sa_Personal_Id");
```

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Set | ObjId.**SetColHidden**(info) |

- **Info**

> **Return**: None

| Parameter     | Type           | 필수여부 | 설 명                      |
| ------------- | -------------- | ---- | ------------------------ |
| info          | object[]       | 필수   | 대상 컬럼 처리 정보 객체 배열 집합     |
| info[].Col    | number /string | 필수   | 대상 컬럼의 Index 또는 SaveName |
| info[].Hidden | boolean        | 필수   | 숨김 여부                    |

- **Example**

```
// 컬럼이 숨겨진 여부를 확인하여 숨겨진 경우 표시되도록 설정한다.
if (mySheet.GetColHidden(1) == 1) {
mySheet.SetColHidden(1, 0);
}
// index 가 3, 6, 7 컬럼에 대한 숨김 처리
mySheet.SetColHidden([
{Col: 3, Hidden:1},
{Col: 6, Hidden:1},
{Col: 7, Hidden:1}
]);
```

- **제공 버전**

| **7.0.0.0**   |                                                 |
| ------------- | ----------------------------------------------- |
| **7.0.13.61** | SetColHidden 메소드의 인자 구조 변경 (기존 방식 처리도 지속적으로 지원) |

> **  **