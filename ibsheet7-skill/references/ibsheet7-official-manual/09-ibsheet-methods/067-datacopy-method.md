# DataCopy Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DataCopy Method

---

- **기능**

> 마지막으로 선택된 데이터 행의 내용을 복사하여 신규 입력 행으로 생성하고, 생성된 행의 Row Index를 반환한다. 트리 형태로 구성된 경우 복사할 대상 행에 자식레벨이 존재할 경우 IncludeChild 인자가 1이면 자식 레벨의 행까지 모두 복사한다.
>
> 신규 생성된 행의 트랜잭션 상태는 "입력"으로 표시된다.

- **Syntax**

|        |                                      |
|:------:|--------------------------------------|
| Syntax | ObjId.**DataCopy**([IncludeChild]) |

- **Info**

> **Return**: Long, 복사하여 생성된 행의 Row Index

| Parameter    | Type    | 필수여부 | 설 명                           |
| ------------ | ------- | ---- | ----------------------------- |
| IncludeChild | Boolean | 선택   | 자식 레벨의 행까지 복사하는지 여부 Default=0 |

- **Example**

```javascript
//행을 복사하고, 복사된 행의 트랜잭션 상태를 "조회"로 변경한다.
//'Status' 는 상태 컬럼의 SaveName
var Row = mySheet.DataCopy();
mySheet.SetCellValue(Row, "Status", "R");
//자식 레벨까지 모두 복사하기
mySheet.DataCopy(1);
```

- **제공 버전**

7.0.0.0