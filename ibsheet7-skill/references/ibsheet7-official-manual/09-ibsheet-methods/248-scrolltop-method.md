# ScrollTop Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ScrollTop Method

---

- **기능**

> 세로 스크롤의 위치를 설정하거나 확인한다.

- **Syntax**

|        |     |                          |
|:------:|:---:|--------------------------|
| Syntax | Get | ObjId.**GetScrollTop**() |

- **Info**

> **Return**: Integer, 현재 설정값

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |

- **Example**

```
//현재 세로 스크롤의 위치를 확인한다.
Console.log("VScrollTopPos : ", mySheet.GetScrollTop());
```

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Set | ObjId.**SetScrollTop**(Pos) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                   |
| --------- | ------ | ---- | --------------------- |
| Pos       | Number | 필수   | 세로 스크롤 위치 (Default:0) |

- **Example**

```
// 현재 세로 스크롤 위치를 30px으로 설정한다.
mySheet.SetScrollTop(30);
```

- **제공 버전**

| **7.0.0.0** |     |
|-------------|-----|

> **  **