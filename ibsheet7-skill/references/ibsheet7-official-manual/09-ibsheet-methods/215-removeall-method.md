# RemoveAll Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RemoveAll Method

---

- **기능**

> 헤더 행을 제외한 모든 데이터 행을 지운다.

- **Syntax**

|        |                                 |
|:------:|---------------------------------|
| Syntax | ObjId.**RemoveAll**([Option]) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                 |
| --------- | ------ | ---- | ------------------- |
| Option    | Object | 선택   | AutoSum 컬럼만 지우도록 설정 |

- **Example**

```javascript
// 모든 데이터 지우기
mySheet.RemoveAll();
// AutoSum 컬럼만 지우기
var Option = { "SumRow" : "AutoSum" };
mySheet.RemoveAll(Option);
```

- **제공 버전**

> **7.0.0.0**