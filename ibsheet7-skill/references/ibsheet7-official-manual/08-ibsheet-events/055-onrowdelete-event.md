# OnRowDelete Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnRowDelete Event

---

- **기능**

> RowDelete 또는 신규행의 DelCheck 타입 클릭 후 발생되는 행 삭제 시점에 발생한다.

- **Syntax**

|        |                                                   |
|:------:|---------------------------------------------------|
| Syntax | **function 오브젝트ID_OnRowDelete**(row, api) { } |

- **Parameters**

|           |         |                                         |
|:---------:|:-------:|:---------------------------------------:|
| Parameter |  Type   |                  설 명                  |
|    row    | number  |              대상 행 Index              |
|    api    | boolean | 메소드(RowDelete) 호출에 의한 삭제 여부 |

- **Example**

```javascript
function mySheet_OnRowDelete(row, api) {
//행 삭제 시 대상 행 및 메소드호출 여부
console.log(“DeleteRow : “ + row + “CallApi : “ +api)
}
```

- **제공 버전**

7.0.13.58