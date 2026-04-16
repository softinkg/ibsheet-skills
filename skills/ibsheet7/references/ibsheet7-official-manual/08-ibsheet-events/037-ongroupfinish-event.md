# ### OnGroupFinish Event

> **IBSheet7 개발자 가이드** > IBSheet Events > ### OnGroupFinish Event

---

- **기능**

> 그룹핑 처리가 완료된 시점에 이 이벤트가 발생한다.

- **Syntax**

|        |                                                    |
|:------:|----------------------------------------------------|
| Syntax | **function 오브젝트ID_ OnGroupFinish**(Group) { } |

- **Parameters**

|           |        |                                                         |
|:---------:|:------:|:-------------------------------------------------------:|
| Parameter |  Type  |                          설 명                          |
|   Group   | String | 그룹 기준 컬럼의 SaveName을 구분자 "\|"로 연결한 문자열 |

- **Example**

```javascript
function mySheet_OnGroupFinish(group) {
console.log("그룹기준 컬럼 : ", group.split("|").join(", "));
}
```

- **제공 버전**

| **7.0.12.1** |     |
|--------------|-----|