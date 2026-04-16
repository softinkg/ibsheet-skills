# Ellipsis Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > Ellipsis Method

---

- **기능**

> 말줄임 표시 기능을 사용할 것인지 여부를 설정하거나 확인한다.
>
> 셀에 설정된 Text의 길이가 해당 컬럼의 너비 보다 클 때 기본적으로 잘려서 표시된다. 이러한 Text를 "…"와 같은 말 줄임 표시로 설정할 때 이 속성을 사용한다.
>
> 이외에도 InitColumns에 Wrap:1속성을 사용하면 내용이 잘리지 않고 자동줄바꿈 기능을 설정하여 사용할 수도 있다.

- **Syntax**

|        |     |                         |
|:------:|:---:|-------------------------|
| Syntax | Get | ObjId.**GetEllipsis**() |

- **Info**

> **Return**: Boolean, 사용가능 여부 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 설정값 확인
mySheet.GetEllipsis();
```

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Set | ObjId.**SetEllipsis**(Flag) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                      |
| --------- | ------- | ---- | ------------------------ |
| Flag      | Boolean | 필수   | 말줄임 표시기능 사용여부, Default=0 |

- **Example**

```
// 말줄임 기능 사용하기
mySheet.SetEllipsis(1);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **