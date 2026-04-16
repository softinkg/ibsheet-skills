# HighlightAfterSort Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > HighlightAfterSort Method

---

- **기능**

> 소트 후 하이라이트 처리 방법을 확인하거나 설정한다.
>
> 설정 가능한 값은 아래와 같다.

| 설정값 | 설명                                      |
|:------:|-------------------------------------------|
|   0    | 포커스 클리어                             |
|   1    | 이전 포커스 유지 및 해당 셀의 위치로 이동 |
|   2    | 이전 포커스 유지 및 scroll 위치 초기화    |

- **Syntax**

|        |     |                                   |
|:------:|:---:|-----------------------------------|
| Syntax | Get | ObjId.**GetHighlightAfterSort**() |

- **Info**

> **Return**: Number, 현재 설정값(Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//소트 이후 설정 확인
mySheet.GetHighlightAfterSort();
```

- **Syntax**

|        |     |                                       |
|:------:|:---:|---------------------------------------|
| Syntax | Set | ObjId.**SetHighlightAfterSort**(Mode) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                         |
| --------- | ------ | ---- | --------------------------- |
| Mode      | Number | 필수   | Sort 후 포커스 설정방법 (Default=1) |

- **Example**

```
//소트 이후 기존에 선택하고 있던 데이터를 찾아감.
mySheet.SetHighlightAfterSort(1);
```

- **제공 버전**

|  **7.0.0.0**  |             |
|:-------------:|-------------|
| **7.0.13.16** | Mode:2 추가 |