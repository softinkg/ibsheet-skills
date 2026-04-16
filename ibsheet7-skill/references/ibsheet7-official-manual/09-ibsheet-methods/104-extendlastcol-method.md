# ExtendLastCol Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ExtendLastCol Method

---

- **기능**

> 마지막 컬럼의 너비를 전체 너비에 맞게 자동으로 맞출것인지 여부를 확인하거나 설정한다.
>
> 이 속성은 Object 너비에 비해서 컬럼 전체 너비의 합이 작을 때 마지막 컬럼을 Object 너비에 맞게 자동으로 넓어지는 기능을 사용하기 위함이다.

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Get | ObjId.**GetExtendLastCol**() |

- **Info**

> **Return**: Boolean, 확장 설정 여부 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```
//설정 여부를 확인한다.
mySheet.GetExtendLastCol()
```

- **Syntax**

|        |     |                                    |
|:------:|:---:|------------------------------------|
| Syntax | Set | ObjId.**SetExtendLastCol**(Extend) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                        |
| --------- | ------- | ---- | -------------------------- |
| Extend    | Boolean | 필수   | 마지막 컬럼 너비 확장 여부 Default= 0 |

- **Example**

```
//마지막 컬럼을 전체 너비에 맞춘다..
mySheet.SetExtendLastCol(1)
```

- **제공 버전**

7.0.0.0