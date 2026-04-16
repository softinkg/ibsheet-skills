# BasicImeMode Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > BasicImeMode Method

---

- **기능**

> Edit 가능한 셀에 포커스가 들어갔을 때 한/영 키보드 상태를 설정하거나 확인한다. 설정할수 있는 값은 아래와 같다.

|         |       |                                 |
|:-------:|:-----:|:-------------------------------:|
| 설정 값 | Value |              설 명              |
| imeAuto |   0   |     마지막 상태 그대로 사용     |
| imeHan  |   1   | 기본 상태를 한글 입력 상태로 함 |
| imeEng  |   2   | 기본 상태를 영문 입력 상태로 함 |

> 단 SetBasicImeMode() 메서드의 사용은 조회 전이나 RemoveAll()메서드를 통해 데이터를 초기화 한 상태에서만 사용이 가능하며 해당 기능은 IE 브라우저에서만 사용이 가능 하다.

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Get | ObjId.**GetBasicImeMode**() |

- **Info**

> **Return**: Integer, 설정값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//기본 한글 입력 키보드 상태 사용
mySheet.GetBasicImeMode();
```

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Set | ObjId.**SetBasicImeMode**(Val) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                   |
| --------- | ------- | ---- | --------------------- |
| Val       | Integer | 필수   | ImeMode 값 Default = 0 |

- **Example**

```
//기본 한글 입력 키보드 상태 사용
mySheet.SetBasicImeMode(1);
```

- **제공 버전**

> **7.0.0.0  **