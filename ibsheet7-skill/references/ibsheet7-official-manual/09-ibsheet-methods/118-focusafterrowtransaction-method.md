# FocusAfterRowTransaction Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > FocusAfterRowTransaction Method

---

- **기능**

> 행 추가, 삭제, 이동, 복사 후 포커스를 이동 할지 여부를 확인 하거나 설정 한다.
>
> 2개 이상의 행에 대한 연속 처리시 불필요한 포커스 처리를 막을 수 있어서 처리 속도를 개선 할 수 있다.

- **Syntax**

|        |     |                                         |
|:------:|:---:|-----------------------------------------|
| Syntax | Get | ObjId.**GetFocusAfterRowTransaction**() |

- **Info**

> **Return**: Boolean, 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 포커스를 이동 할지 여부를 확인
mySheet.GetFocusAfterRowTransaction();
```

- **Syntax**

|        |     |                                             |
|:------:|:---:|---------------------------------------------|
| Syntax | Set | ObjId.**SetFocusAfterRowTransaction**(mode) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                   |
| --------- | ------- | ---- | --------------------- |
| mode      | Boolean | 필수   | 포커스 설정 여부 (Default=1) |

- **Example**

```javascript
// 현재 포커스행 하위로 10개 행을 추가후 맨 마지막 추가된 행에 포커스 설정
mySheet.SetFocusAfterRowTransaction(0);
var new Row = null;
for (var i = 0; I < 10; i++) {
newRow = mySheet.DataInsert();
}
mySheet.SetSelectRow(newRow);
```

- **제공 버전**

7.0.0.0