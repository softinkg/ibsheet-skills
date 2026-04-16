# RedrawSum Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RedrawSum Method

---

- **기능**

> 합계 내용 계산 여부를 확인하거나 설정한다.
>
> 합계를 표시하는 컬럼의 값을 SetCellValue Method등으로 변경하면 합계를 계산하느라고 속도가 느려지는 증상이 발생한다. 하나의 데이터를 설정하면서 합계를 다시 계산하기 때문이다. 이때 데이터를 모두 변경한 다음에 합계를 계산하는 기능을 설정함으로써 데이터 변경의 속도를 향상시킬수 있다. 이 속성에 주의할 점은 0으로 사용 후 반드시 1로 설정 하여야 한다.

- **Syntax**

|        |     |                          |
|:------:|:---:|--------------------------|
| Syntax | Get | ObjId.**GetRedrawSum**() |

- **Info**

> **Return**: Boolean, 설졍 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//합계 내용 계산 여부를 확인한다.
mySheet.GetRedrawSum();
```

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Set | ObjId.**SetRedrawSum**(Redraw) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명       |
| --------- | ------- | ---- | --------- |
| Redraw    | Boolean | 필수   | 합계행 계산 여부 |

- **Example**

```javascript
//변경해야 할 데이터가 많은 경우 사용
mySheet.SetRedrawSum(0);
for(var i=1; i<100; i++) mySheet.SetCellValue(i,1, 10000, 0);
//RedrawSum 가 1가 되는 순간 합계와 데이터가 한꺼번에 표시
mySheet.SetRedrawSum(1);
```

- **제공 버전**

7.0.0.0