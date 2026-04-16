# Enable Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > Enable Method

---

- **기능**

> 이 속성값을 0로 설정하면 마우스나 키보드를 사용한 User Interface 기능은 모두 사용 불가능하고, 기타 제품이 제공하는 Method나 Property는 코딩으로 호출되므로 사용할수 있다.

- **Syntax**

|        |     |                       |
|:------:|:---:|-----------------------|
| Syntax | Get | ObjId.**GetEnable**() |

- **Info**

> **Return**: Boolean, 사용가능 여부 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//User Interface 사용가능 여부 값을 확인한다.
mySheet.GetEnable();
```

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Set | ObjId.**SetEnable**(Enable) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                     |
| --------- | ------- | ---- | ----------------------- |
| Enable    | Boolean | 필수   | User Interface 사용 가능 여부 |

- **Example**

```
//사용 불가능 상태로 변경한다.
mySheet.SetEnable(0);
//사용 가능 상태로 변경한다.
mySheet.SetEnable(1);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **