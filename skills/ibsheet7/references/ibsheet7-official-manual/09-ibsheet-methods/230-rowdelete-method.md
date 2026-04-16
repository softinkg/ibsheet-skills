# RowDelete Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowDelete Method

---

- **기능**

> 특정의 단일 또는 다중 데이터 행을 삭제 한다.
>
> Confirm 인자를 1로 설정한 경우 삭제 전 확인 메시지를 표시 한다.
>
> Row 인자를 설정하지 않은 경우 현재 선택되어 있는 행에 대해서 기능을 수행 한다.

- **Syntax**

|        |                                          |
|:------:|------------------------------------------|
| Syntax | ObjId.**RowDelete**([Row],[Confirm]) |

- **Info**

> **Return**: None

| Parameter | Type          | 필수여부 | 설 명                                                                 |
| --------- | ------------- | ---- | ------------------------------------------------------------------- |
| Row       | Number/String | 선택   | 삭제할 행의 Row Index, 또는 행의 Index를 "\|" 구분자로 연결한 문자열 Default ="현재 선택 행" |
| Confirm   | Boolean       | 선택   | 삭제 전 메세지 표시 여부 Default=0                                            |

- **Example**

```
//확인 메시지 없이 1행 삭제하기
mySheet.RowDelete(1, 0);
// 3, 7, 10번 행 삭제하기
mySheet.RowDelete("3|7|10");
```

- **제공 버전**

> **7.0.0.0  **