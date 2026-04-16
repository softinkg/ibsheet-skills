# InitComboNoMatchText Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > InitComboNoMatchText Method

---

- **기능**

> Combo 항목을 표시 시, Combo 항목에 없는 항목을 설정하거나 조회 하였을 경우 보여지는 글자를 설정한다.
>
> Show 인자를 1(true)로 설정 하면 조회데이터의 내용이 ComboCode에 해당하는 값이 존재하지 않는 경우 Text 인자에 설정한 값이 보여진다.
>
> Insert 인자를 1(true)로 설정할 경우, InitColumns 에서 설정한 적이 없는 ComboText 또는 ComboCode 값이 조회되면 그 값으로 아이템을 추가한다.

- **Syntax**

|  |  |
|:--:|----|
| Syntax | ObjId.**InitComboNoMatchText**(Show, [Text], [Insert], [Auto]) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                                |
| --------- | ------- | ---- | ---------------------------------- |
| Show      | Boolean | 필수   | 항목에 없는 데이터를 보여줄지 여부                |
| Text      | String  | 선택   | 항목에 없는 데이터 대신 표시할 문자열              |
| Insert    | Boolean | 선택   | 해당 데이터를 항목에 추가 할지 여부               |
| Auto      | Boolean | 선택   | 해당 데이터를 표시만 하고 항목에는 추가하지 않도록 설정 여부 |

- **Example**

```
//Combo 항목이 없는 경우 항목 없음 표시하기
mySheet.InitComboNoMatchText(1, "항목없음");
```

- **제공 버전**

|  **7.0.0.0**  |                |
|:-------------:|----------------|
| **7.0.13.98** | Auto 속성 추가 |