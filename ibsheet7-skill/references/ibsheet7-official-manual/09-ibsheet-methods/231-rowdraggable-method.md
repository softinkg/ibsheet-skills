# RowDraggable Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RowDraggable Method

---

- **기능**

> 특정 행의 마우스 드래그 가능여부를 설정하거나 확인 한다.
>
> 설정 값에 따른 처리방식은 아래와 같다.

| 설정값         | 내용       |
| ----------- | -------- |
| 0           | 행 드래그 불가 |
| 1 (Default) | 행 드래그 가능 |

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Get | ObjId.**GetRowDraggable**(row) |

- **Info**

> **Return**: Boolean, 설정된 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명          |
| --------- | ---- | ---- | ------------ |
| row       | Long | 선택   | 행의 Row Index |

- **Example**

```javascript
// Drag 가능여부 설정 값 확인
var drag = mySheet.GetRowDraggable(3);
```

- **Syntax**

|        |     |                                      |
|:------:|:---:|--------------------------------------|
| Syntax | Set | ObjId.**SetRowDraggable**(row, drag) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                       |
| --------- | ------- | ---- | ------------------------- |
| row       | Long    | 선택   | 행의 Row Index              |
| drag      | Boolean | 필수   | 드래그 가능여부 설정 값 (Default=1) |

- **Example**

```
// 3행의 Drag 가능여부 설정 (마우스 드래깅시 행 드래깅 가능여부 설정)
mySheet.SetRowDraggable(3, 1); // 드래그 가능
mySheet.SetRowDraggable(3, 0); // 드래그 불가
```

- **제공 버전**

> **7.0.0.0**