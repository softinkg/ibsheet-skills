# HideGroupRow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > HideGroupRow Method

---

- **기능**

> 시트의 그룹행을 삭제하거나 숨김처리 한다.
>
> 그룹행 삭제시에는 그룹핑 상태인 경우 모두 초기화 되며 숨김시에는 그룹핑 상태가 그대로 유지 된다.
>
> 숨김상태인 경우 ShowGroupRow 메소드를 통해 보이도록 처리할 수 있다.

- **Syntax**

|        |                                 |
|:------:|---------------------------------|
| Syntax | ObjId.**HideGroupRow**([Del]) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                 |
| --------- | ------- | ---- | ------------------- |
| Del       | Boolean | 선택   | 삭제 여부 (Default="1") |

- **Example**

```
//그룹행 삭제
mySheet.HideGroupRow();
// 그룹행 숨김
mySheet.HideGroupRow(0)
```

- **제공 버전**

| **7.0.10.0** |     |
|--------------|-----|