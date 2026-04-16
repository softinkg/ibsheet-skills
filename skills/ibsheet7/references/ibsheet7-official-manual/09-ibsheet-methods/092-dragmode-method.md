# DragMode Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DragMode Method

---

- **기능**

> 마우스 드래깅시 처리 방법을 설정하거나 확인 한다.
>
> 설정 값에 따른 처리방식은 아래와 같다.

| 설정값         | 내용          |               |
| ----------- | ----------- | ------------- |
| 0 (Default) | 일반          | 셀 또는 행 범위 셀렉션 |
| 0 (Default) | Ctrl Key 사용 | 행 드래깅         |
| 1           | 일반          | 행 드래깅         |
| 1           | Ctrl Key 사용 | 셀 또는 행 범위 셀렉션 |

- **Syntax**

|        |     |                         |
|:------:|:---:|-------------------------|
| Syntax | Get | ObjId.**GetDragMode**() |

- **Info**

> **Return**: Boolean, 설정된 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```javascript
//DragMode 설정 값 확인
var mode = mySheet.GetDragMode();
```

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Set | ObjId.**SetDragMode**(Mode) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                     |
| --------- | ------- | ---- | ----------------------- |
| Mode      | Boolean | 필수   | 드래그 처리 설정 값 (Default=0) |

- **Example**

```
// DragMode 방식 설정 (마우스 드래깅시 행 드래깅 처리 방식 설정)
mySheet.SetDragMode(1);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **