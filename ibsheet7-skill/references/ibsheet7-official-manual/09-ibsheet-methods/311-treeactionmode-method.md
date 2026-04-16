# TreeActionMode Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > TreeActionMode Method

---

- **기능**

> 트리 형태일때 각종 기능 처리 관련 속성을 확인하거나 설정한다.
>
> 속성값은 다음과 같다.

| 설정값 | 기능                                             |
| --- | ---------------------------------------------- |
| 0   | 자식이 있으면 삭제 안됨, 부모가 삭제이면 삭제 취소 할수 없음, (Default) |
| 1   | 삭제 체크시 자식까지 삭제 체크됨                             |

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Get | ObjId.**GetTreeActionMode**() |

- **Info**

> **Return**: Integer, 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//현재 설정되어 있는 TreeActionMode 값 확인한다.
Alert(mySheet.GetTreeActionMode());
```

- **Syntax**

|        |     |                                    |
|:------:|:---:|------------------------------------|
| Syntax | Set | ObjId.**SetTreeActionMode**(Value) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명              |
| --------- | ------- | ---- | ---------------- |
| Value     | Integer | 필수   | TreeActionMode 값 |

- **Example**

```
//삭제 체크를 눌렀을 때 자식레벨까지 삭제되도록 한다.
mySheet.SetTreeActionMode(1);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **