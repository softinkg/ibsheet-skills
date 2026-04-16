# PagingPosition Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > PagingPosition Method

---

- **기능**

> 페이지 네비게이션을 사용여부를 설정하거나 확인 한다.
>
> 사용시 건수 정보 영역에 설정값에 따라 좌측 또는 우측에 표시되며, CountPosition 설정이 1 ~ 4의 값으로 설정이 되어 있어야 한다.
>
> 건수 정보 또는 선택 요약 정보의 설정보다 페이지 네비게이션 설정이 우선시 되기 때문에 페이지 네비게이션 설정영역에 위치한 건수 정보 또는 선택 요약 정보는 표시 되지 않는다.
>
> 페이지 네비게이션이 불필요한 조회모드를 설정한 경우 설정값과 상관없이 0으로 설정 된다 (SearchMode:smGeneral)
>
> 설정 값 별로 개수 정보 표시 영역 정보는 다음과 같다.

|          |               |      |      |
|:--------:|:-------------:|:----:|:----:|
|  설정값  |       0       |  1   |  2   |
| 표시위치 | 표시하지 않음 | 좌측 | 우측 |

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Get | ObjId.**GetPagingPosition**() |

- **Info**

> **Return**: Number, 페이지 네비게이션의 설정 위치 값

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 현재 설정된 페이지 네비게이션 설정 위치값을 확인 한다.
mySheet.GetPagingPosition()
```

- **Syntax**

|        |     |                                       |
|:------:|:---:|---------------------------------------|
| Syntax | Set | ObjId.**SetPagingPosition**(Position) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                |
| --------- | ------ | ---- | ------------------ |
| Position  | Number | 필수   | 설정할 페이지 네비게이션 위치 값 |

- **Example**

```
// 페이지 네이게이션을 좌측 상단, 건수 정보를 우측 상단에 표시 한다.
mySheet.SetCountPosition(2);
mySheet.SetPagingPosition(1)
```

- **제공 버전**

> **7.0.0.0**
>
> **  **