# RowData Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowData Method

---

- **기능**

> 행의 데이터를 각 컬럼의 SaveName을 이용하여 Json 객체로 생성하여 반환하거나 설정한다.
>
> 2개행 이상의 단위데이터행 구조인 경우 단위데이터행 전체를 반환하거나 설정한다.

- **Syntax**

|        |                           |
|:------:|---------------------------|
| Syntax | ObjId.**GetRowData**(Row) |

- **Info**

> **Return**: Object, 해당 행의 데이터 객체

| Parameter | Type   | 필수여부 | 설 명         |
| --------- | ------ | ---- | ----------- |
| Row       | Number | 필수   | 대상 행의 Index |

- **Example**

```javascript
// 1행의 Json 객체를 가져온다.
var rowJosn = mySheet.GetRowData(1);
```

- **Syntax**

|        |                                      |
|:------:|--------------------------------------|
| Syntax | ObjId.**SetRowData**(Row, Data, Opt) |

- **Info**

> **Return**: Object, 해당 행의 데이터 객체

| Parameter      | Type           | 필수여부 | 설 명                                                                                                          |
| -------------- | -------------- | ---- | ------------------------------------------------------------------------------------------------------------ |
| Row            | Number         | 필수   | 대상 행 또는 추가할 위치의 Row Index                                                                                    |
| Data           | Object/ String | 필수   | Json 형태의 행 데이터 객체 또는 문자열                                                                                     |
| Opt.Add        | Boolean        | 선택   | 행 추가 여부 (Default=0)                                                                                          |
| Opt.Level      | Number         | 선택   | 트리구조에서 행 추가인 경우 추가될 행의 트리 레벨 값                                                                               |
| Opt.Event.     | Boolean        | 선택   | 셀값 변경시 OnChange 이벤트 발생 여부 (Default = 1)                                                                      |
| Opt.StatusMode | Number         | 선택   | 상태값 처리 모드 (Default = 1) 0 : 대상 행의 상태값을 변경하지 않음 1 : 인자의 상태값을 무시하고 대상 행의 데이터 변경에 따른 상태값 처리 2 : 인자의 상태값을 그대로 적용 |

- **Example**

```javascript
// 1행을 해당 Json 객체로 설정한다.
var data = {sName:"홍길동", sAge:20};
mySheet.SetRowData(1, data);
// 1행의 데이터를 2행에 적용
mySheet.SetRowData(2, mySheet.GetRowData(1));
```

- **제공 버전**

| **7.0.5.0** |     |
|-------------|-----|

> **  **