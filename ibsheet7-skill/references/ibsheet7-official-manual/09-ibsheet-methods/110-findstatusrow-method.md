# FindStatusRow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > FindStatusRow Method

---

- **기능**

> 트랜잭션 상태에 해당하는 행번호를 ";"로 조합하여 반환한다.
>
> 트랜잭션 상태는 RIUD의 문자열을 "\|"로 연결하여 설정하면 해당하는 트랜잭션인 행의 번호를 모두 찾아서 "\|"로 조합하여 반환한다.

- **Syntax**

|        |                                  |
|:------:|----------------------------------|
| Syntax | ObjId.**FindStatusRow**(sStatus) |

- **Info**

> **Return**: String, 트랜잭션 상태에 해당하는 행번호를 ";"로 조합한 문자열(Default="")

| Parameter | Type   | 필수여부 | 설 명                              |
| --------- | ------ | ---- | -------------------------------- |
| sStatus   | String | 필수   | 찾고자 하는 트랜잭션 상태 코드를 "\|"로 연결한 문자열 |

- **Example**

```javascript
// 수정, 삭제인 행을 알아오기
//인자->U|D, 결과->1;3;4;5;6
var sRow = mySheet.FindStatusRow("U|D");
//받은 결과를 배열로 생성한다.
var arrow = sRow.split(";");
```

- **제공 버전**

> **7.0.0.0  **