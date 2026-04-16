# EditTabBehavior Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > EditTabBehavior Method

---

- **기능**

> 데이터를 Edit 후 Tab 키를 눌렀을 때 동작을 확인하거나 설정한다
>
> 설정값에 대한 동작은 다음과 같다.

|  |  |
|:--:|:--:|
| 값 | 설명 |
| 0 | 다음 편집이 가능한 셀로 이동 (편집상태 유지) |
| 1 | 편집여부와 무관하게 다음셀로 이동 (다음셀이 편집 가능한 경우면 편집상태 유지) |
| 2 | 편집여부와 무관하게 다음셀로 이동 (다음셀의 편집 가능여부와 무관하게 편집상태 종료) |

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Get | ObjId.**GetEditTabBehavior**() |

- **Info**

> **Return**: String, 설정한 속성 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// Tab키의 동작을 확인한다.
mySheet.GetEditTabBehavior();
```

- **Syntax**

|        |     |                                    |
|:------:|:---:|------------------------------------|
| Syntax | Set | ObjId.**SetEditTabBehavior**(Mode) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                                      |
| --------- | ------ | ---- | ---------------------------------------- |
| Mode      | Number | 필수   | 편집상태에서 Tab key 입력시 설정할 속성 값. Default="0" |

- **Example**

```
// Edit 후 Tab을 누르면 무조건 다음 셀로 이동하게 한다.
mySheet.SetEditTabBehavior(1);
```

- **제공 버전**

> **7.0.0.0**

**  **