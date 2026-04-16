# Editable Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > Editable Method

---

- **기능**

> 전체적인 Edit 허용 여부를 확인하거나 설정한다.
>
> 전체적으로 Edit가 불가능하면 다른 설정에 관계없이 모든 Edit는 불가능하다.
>
> 전체 Edit 가능 여부는 다음과 같이 결정된다.

|              |             |             |              |                         |
|:------------:|:-----------:|:-----------:|:------------:|:-----------------------:|
| **Editable** | ColEditable | RowEditable | CellEditable | **셀의 Edit 가능 여부** |
|   **불가**   |    무관     |    무관     |     무관     |        **불가**         |
|   **가능**   |    불가     |    불가     |  가능/불가   |      **가능/불가**      |
|   **가능**   |    가능     |  가능/불가  |  가능/불가   |      **가능/불가**      |

- **Syntax**

|        |     |                         |
|:------:|:---:|-------------------------|
| Syntax | Get | ObjId.**GetEditable**() |

- **Info**

> **Return**: Boolean, 설정된 편집 여부 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//Edit 가능 여부 확인
mySheet.GetEditable();
```

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Set | ObjId.**SetEditable**(Edit) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명         |
| --------- | ------- | ---- | ----------- |
| Edit      | Boolean | 필수   | 설정할 편집 여부 값 |

- **Example**

```
//초기 로드 시 전체 적인 Edit 가능 설정
mySheet.SetEditable(1);
```

- **제공 버전**

> **7.0.0.0  **