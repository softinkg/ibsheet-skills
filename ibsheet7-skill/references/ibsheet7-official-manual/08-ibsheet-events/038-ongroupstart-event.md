# ### OnGroupStart Event

> **IBSheet7 개발자 가이드** > IBSheet Events > ### OnGroupStart Event

---

- **기능**

> 그룹핑 처리가 되기전 시점에 이 이벤트가 발생한다.

- **Syntax**

|        |                                                  |
|:------:|--------------------------------------------------|
| Syntax | **function 오브젝트ID_ OnGroupStart**(cols) { } |

- **Parameters**

|           |        |                |
|:---------:|:------:|:--------------:|
| Parameter |  Type  |     설 명      |
|   cols    | String | 그룹 컬럼 정보 |

- **Example**

```javascript
function mySheet_OnGroupStart(cols) {
//현재 Group 중인 컬럼
console.log("Group : " + col);
}
```

- **제공 버전**

| **7.0.13.83** |     |
|---------------|-----|