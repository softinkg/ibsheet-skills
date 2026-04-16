# TotalRows Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > TotalRows Method

---

- **기능**

> 조회 조건에 따라 전체 조회해야 할 DB의 레코드 건수를 확인하거나 설정한다.

- **Syntax**

|        |     |                          |
|:------:|:---:|--------------------------|
| Syntax | Get | ObjId.**GetTotalRows**() |

- **Info**

> **Return**: Long, 현재 설정된 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//전체 데이터 건수를 확인한다.
Alert("전체 데이터 건수는 " + mySheet.GetTotalRows() + "입니다. ");
```

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Set | ObjId.**SetTotalRows**(Count) |

- **Info**

> **Return**: None

| Parameter | Type | 필수여부 | 설 명       |
| --------- | ---- | ---- | --------- |
| Count     | Long | 필수   | 전체 건수 설정값 |

- **Example**

```
//전체 데이터 건수를 1000으로 설정한다.
mySheet.SetTotalRows(1000);
```

- **제공 버전**

> **7.0.0.0**