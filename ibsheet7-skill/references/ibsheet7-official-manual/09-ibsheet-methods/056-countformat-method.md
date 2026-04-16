# CountFormat Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CountFormat Method

---

- **기능**

> 보여지는 건수 정보의 포멧을 확인하거나 설정한다. 건수 정보는 사용 가능한 예약어의 조합으로 구성되는데 가능한 예약어의 아래와 같다.

| 예 약 어            | 설 명                                                                                                    |
| ---------------- | ------------------------------------------------------------------------------------------------------ |
| "BOTTOMDATA"     | 바닥 데이터 행번                                                                                              |
| "TOTALROWS"      | DB 전체 데이터 건수 1) 조회된 전체데이타 건수 2) 사용자가 세팅 위 2단계중 맨 마지막에 세팅된 값이 TOTALROWS로 보여지게 된다.                       |
| BOTTOMDATA2      | 바닥 데이터 행번(소계, 누계행 제외)                                                                                  |
| TOTALROWS2       | DB 전체 데이터 건수(소계, 누계행 제외)                                                                               |
| "SEARCHROWS"     | 조회된 데이터 건수 ( 상태값이 ""만 카운트 )                                                                            |
| "INSERTROWS"     | 입력 건수 (상태값이 "I"만 카운트)                                                                                  |
| "UPDATEROWS"     | 수정 건수 (상태값이 "U"만 카운트)                                                                                  |
| "DELETEROWS"     | 삭제 건수 (상태값이 "D"만 카운트)                                                                                  |
| "ROWCOUNT"       | 전체(입력+수정+삭제) 건수                                                                                        |
| "SELECTDATAROW"  | 현재 포커스 선택된 행의 레코드 순서 숨겨진 행은 개수에 포함한다. 합계와 소계는 레코드 개수에서 제외한다. 2줄 이상이 한 레코드인 경우 행의 순서가 아니라 레코드 순서로 표시한다. |
| " FILTEREDCOUNT" | 필터링 된 행의 개수                                                                                            |
| “HIDDENROWS”     | 숨겨진 행                                                                                                  |
| “EXCEPTHIDE”     | 숨겨진 행을 제외한 서버 페이징 전체 행 (TOTALROWS - HIDDENROWS)                                                        |
| “ROWVIEWCOUNT”   | 숨겨진 행을 제외한 전체 행 (ROWCOUNT-HIDDENROWS)                                                                  |

> 기본 포멧은 "[BOTTOMDATA / TOTALROWS]"으로 구성되어 있다.

- **Syntax**

|        |     |                            |
|:------:|:---:|----------------------------|
| Syntax | Get | ObjId.**GetCountFormat**() |

- **Info**

> **Return**: Sring, 설정된 출력 포맷 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//건수 포멧을 확인한다.
mySheet.GetCountFormat();
```

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Set | ObjId.**SetCountFormat**(Format) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명      |
| --------- | ------ | ---- | -------- |
| Format    | String | 필수   | 설정할 출력포맷 |

- **Example**

```
//건수 포멧을 설정한다.
mySheet.SetCountFormat("현재 BOTTOMDATA건 / 전체 TOTALROWS건");
//포커스로 표시한다.
mySheet.SetCountFormat("선택 SELECTDATAROW행 / 총 ROWCOUNT건");
```

- **제공 버전**

| **7.0.0.0** |  |
|:--:|:---|
| **7.0.13.108** | HIDDENROWS, EXCEPTHIDE, ROWVIEWCOUNT FILTEREDVIEWCOUNT 예약어 추가 |
| **7.0.13.126** | BOTTOMDATA2, TOTALROWS2 예약어 추가 |

> **  **