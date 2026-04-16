# SelectCol Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SelectCol Method

---

- **기능**

> 현재 선택된 셀의 컬럼 Index를 확인하거나 설정한다.
>
> SelectRow 속성과 함께 사용하며, 두 속성을 모두 사용한 SelectCell 함수를 이용할 수 있다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 모든행에 대해서 처리를 하고 SaveName으로 설정할 경우 해당 SaveName이 포함된 행에 대해서만 처리 한다.

- **Syntax**

|        |     |                          |
|:------:|:---:|--------------------------|
| Syntax | Get | ObjId.**GetSelectCol**() |

- **Info**

> **Return**: Number, 현재 선택된 컬럼 Index (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```
//선택된 컬럼을 확인한다.
Alert(mySheet.GetSelectCol());
```

- **Syntax**

|        |     |                                           |
|:------:|:---:|-------------------------------------------|
| Syntax | Set | ObjId.**SetSelectCol**(Col, [UseEvent]) |

- **Info**

> **Return**: None

| Parameter | Type            | 필수여부 | 설 명                                         |
| --------- | --------------- | ---- | ------------------------------------------- |
| Col       | Number / String | 필수   | 현재 선택된 셀의 Column Index 또는 SaveName          |
| UseEvent  | Boolean         | 선택   | OnSelectCell 이벤트 발생 여부 Default = 1 (이벤트 발생) |

- **Example**

```
//인덱스가 2인 컬럼을 선택한다.
mySheet.SetSelectCol(2);
```

- **제공 버전**

> **7.0.0.0**