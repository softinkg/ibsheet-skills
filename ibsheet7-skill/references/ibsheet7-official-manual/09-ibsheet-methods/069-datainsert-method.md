# DataInsert Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DataInsert Method

---

- **기능**

> 데이터 행을 신규 생성하고, 생성된 행의 Row Index를 반환한다.
>
> Row인자와 Level인자는 다음과 같이 설정된다.

|  |  |  |
|:--:|:--:|:--:|
| Row 설정값 | 생성 행 위치 | Level |
| Row < 0 | 마지막 행에 생성 | 0레벨 |
| Row >= 전체 행 | 마지막 행에 생성 | 0레벨 |
| Row < 데이터 첫 행 | 첫 행에 생성 | 0레벨 |
| 그 외 | 해당 행에 생성 | 설정 레벨 |
| 기 본 | 선택된 행 아래 생성 | 설정 값이 없는 경우 선택 행의 자식 레벨 |

> 트리 구조시 Level인자는 값을 설정하지 않으면 기본적으로 선택 행의 자식 레벨로 생성한다. 만약 선택 행이 삭제 상태라면 에러 메시지를 표시하고 신규 생성 처리를 중단한다.

- **Syntax**

|        |                                                   |
|:------:|---------------------------------------------------|
| Syntax | ObjId.**DataInsert**([Row], [Level], [Opt]) |

- **Info**

> **Return**: Long, 신규 생성된 행의 Row Index

| Parameter     | Type    | 필수여부 | 설 명                                                       |
| ------------- | ------- | ---- | --------------------------------------------------------- |
| Row           | Long    | 선택   | 생성될 행 위치, Default="마지막 선택 행 바로 아래"                        |
| Level         | Long    | 선택   | 생성될 행의 트리 레벨 수준, Default="마지막 선택 행의 레벨보다 1큰 레벨로, 자식으로 생성" |
| Opt.Focus     | Boolean | 선택   | 생성된 행으로 포커스가 이동할 지 여부 Default = 1                         |
| Opt.CellEvent | Boolean | 선택   | OnSelectCell 이벤트 발생 여부 Default = 1                        |

- **Example**

```
//첫 행에 생성하기
mySheet.DataInsert(0);
//마지막 행에 생성하기
mySheet.DataInsert(-1);
//현재 선택된 행의 바로 아래에 생성
mySheet.DataInsert();
//7 행에 생성
mySheet.DataInsert(7);
```

- **제공 버전**

|  **7.0.0.0**   |                 |
|:--------------:|-----------------|
| **7.0.13.112** | Focus 인자 추가 |