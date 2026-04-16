# SelectionMode Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SelectionMode Method

---

- **기능**

> 셀 선택 모드를 설정하거나 확인한다. 설정가능한 종류는 아래와 같다.

| 종류  | 설명                                                                                                         |
| --- | ---------------------------------------------------------------------------------------------------------- |
| 0   | 셀 단위 선택                                                                                                    |
| 1   | 행 단위 선택                                                                                                    |
| 3   | Ctrl 키를 이용하여 연결되지 않은 다중의 행을 선택 선택된 행번은 GetSelectionRows() 함수 이용 확인                                         |
| 4   | 행 전체 선택 행 전체에 대한 동일한 색상을 지정할 때 사용 Focus 및 Hover 행에 대해 대해 모두 적용                                             |
| 5   | 단위데이터행, 앞컬럼 머지(머지가능 컬럼중 첫번째 기준)행의 영역 선택 Ctrl 키를 이용하여 연결되지 않은 다중의 행을 선택 선택된 행번은 GetSelectionRows() 함수 이용 확인 |

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Get | ObjId.**GetSelectionMode**() |

- **Info**

> **Return**: Integer, 현재 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 현재 설정되어 있는 선택 모드를 확인한다.
Alert(mySheet.GetSelectionMode());
```

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Set | ObjId.**SetSelectionMode**(Mode) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                         |
| --------- | ------- | ---- | --------------------------- |
| Mode      | Integer | 필수   | 선택 모드 종류 (0 : 셀단위, 1 : 행단위) |

- **Example**

```
//셀 단위 선택으로 설정한다.
mySheet.SetSelectionMode(0);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **