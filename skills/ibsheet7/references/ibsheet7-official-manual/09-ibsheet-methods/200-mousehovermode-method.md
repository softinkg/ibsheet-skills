# MouseHoverMode Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > MouseHoverMode Method

---

- **기능**

> 시트내의 행 또는 셀에 마우스 커서가 위치했을 때 Hover 동작 모드를 설정한다.

|        |                    |
|:------:|:------------------:|
| 설정값 |        설명        |
|   0    | 사용안함 (Default) |
|   1    |    셀단위 Hover    |
|   2    |    행단위 Hover    |

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Get | ObjId.**GetMouseHoverMode**() |

- **Info**

> **Return**: String, 마우스 Hover 모드 설정 값

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//마우스 Hover 모드 설정값을 확인한다.
mySheet.GetMouseHoverMode();
```

- **Syntax**

|        |     |                                   |
|:------:|:---:|-----------------------------------|
| Syntax | Set | ObjId.**SetMouseHoverMode**(Mode) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명      |
| --------- | ------ | ---- | -------- |
| Mode      | Number | 필수   | 설정할 모드 값 |

- **Example**

```
//마우스 Hover 모드를 행단위로 설정 한다.
mySheet.SetMouseHoverMode(2);
```

- **제공 버전**

| **7.0.8.0** |     |
|-------------|-----|

> **  **