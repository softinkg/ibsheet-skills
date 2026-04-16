# FrozenCol Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > FrozenCol Method

---

- **기능**

> 좌측 고정컬럼을 동적으로 설정한다.
>
> 설정한 개수의 열을 고정열로 출력한다.
>
> 기존에 설정된 고정컬럼 수 보다 많은 수를 설정하는 경우 추가로 고정컬럼을 설정 처리하고, 적은 수를 설정한 경우 초과되는 컬럼수만큼 고정컬럼을 해제 처리한다.
>
> 메인 섹션의 컬럼을 모두 고정으로 설정하는 경우 및 시트에서 보여지는 영역내에서 설정한 고정컬럼을 모두 표현할 수 없는 경우 시트가 정상적으로 동작하지 않을 수 있다. (주의)

- **Syntax**

|        |     |                          |
|:------:|:---:|--------------------------|
| Syntax | Get | ObjId.**GetFrozenCol**() |

- **Info**

> **Return**: Integer, 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 고정컬럼 설정 값을 확인한다.
Alert(mySheet.GetFrozenCol());
```

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Set | ObjId.**SetFrozenCol**(Count) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                     |
| --------- | ------- | ---- | ----------------------- |
| Rows      | Integer | 필수   | 설정할 고정컬럼 개수 (Default=0) |

- **Example**

```
// 3개의 고정컬럼을 설정한다.
mySheet.SetFrozenCol(3);
```

- **제공 버전**

7.0.0.0

> **  **