# RowTop Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowTop Method

---

- **기능**

> 특정 행의 상단 시작위치의 offsetTop 값을 확인 한다.
>
> Row 인자 설정이 잘못된 경우는 별도 처리없이 -1을 리턴 한다.
>
> 시트 컨테이너(table)의 최상단위치를 기준으로하여 처리 된다. (기준점 : 0)
>
> 동일한 행인 경우에도 세로 스크롤 위치에 따라서 반환값이 달라질 수 있다.

- **Syntax**

|        |                       |
|:------:|-----------------------|
| Syntax | ObjId.**RowTop**(Row) |

- **Info**

| Type      | Long, 행의 상단 위치 |           |
| --------- | -------------- | --------- |
| Parameter | Type           | 설 명       |
| Row       | Long           | Row Index |

- **Example**

```javascript
//행의 상단 위치를 파악한다.
var iTop = mySheet.RowTop(1);
```

- **제공 버전**

7.0.0.0