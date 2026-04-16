# ColEditable Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ColEditable Method

---

- **기능**

> 특정 컬럼의 Edit 가능 여부를 확인하거나 설정한다.
>
> 특정 컬럼의 Edit 가능 여부는 전체 Edit 가능 여부가 가능일 때 변경 가능하다. 단, ColEditable 설정값이 불가인 경우는 RowEditable 설정이 무시된다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 모든행에 대해서 처리를 하고 SaveName으로 설정할 경우 해당 SaveName이 포함된 행에 대해서만 처리 한다.
>
> 특정 컬럼의 Edit 가능 여부는 다음과 같이 결정된다.

|          |                 |             |              |                         |
|:--------:|:---------------:|:-----------:|:------------:|:-----------------------:|
| Editable | **ColEditable** | RowEditable | CellEditable | **셀의 Edit 가능 여부** |
|   불가   |    **무관**     |    무관     |     무관     |        **불가**         |
|   가능   |    **불가**     |    불가     |  가능/불가   |      **가능/불가**      |
|   가능   |    **가능**     |  가능/불가  |  가능/불가   |      **가능/불가**      |

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Get | ObjId.**GetColEditable**(Col) |

- **Info**

> **Return**: Boolean, Edit 가능 여부 (Get Method 인 경우)

| Parameter | Type         | 필수여부 | 설 명                             |
| --------- | ------------ | ---- | ------------------------------- |
| Col       | Long /String | 필수   | 특정 컬럼의 Column Index 또는 SaveName |

- **Example**

```
//5컬럼의 Edit 가능 여부를 확인한다.
mySheet. GetColEditable (5);
```

- **Syntax**

|        |     |                                         |
|:------:|:---:|-----------------------------------------|
| Syntax | Set | ObjId.**SetColEditable**(Col, Editable) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                             |
| --------- | ------------ | ---- | ------------------------------- |
| Col       | Long /String | 필수   | 특정 컬럼의 Column Index 또는 SaveName |
| Editable  | Boolean      | 필수   | 특정컬럼의 Edit 가능 여부 (Set일때만 사용)    |

- **Example**

```
//5컬럼의 Edit 가능 여부를 불가로 설정한다.
mySheet.SetColEditable(5,0);
//5컬럼의 Edit 가능 여부를 가능으로 설정한다.
mySheet. SetColEditable (5,1);
```

- **제공 버전**

**7.0.0.0**

**  **