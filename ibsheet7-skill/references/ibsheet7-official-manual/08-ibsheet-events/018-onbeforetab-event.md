# ### OnBeforeTab Event

> **IBSheet7 개발자 가이드** > IBSheet Events > ### OnBeforeTab Event

---

- **기능**

> 시트에서 탭 키를 누르는 경우 탭 이벤트가 발생전에 발생한다.
>
> 리턴값이 false 또는 0인 경우 해당 셀에서 포커스를 이동하지 않는다.
>
> 편집중인 셀의 경우 편집만 완료한다.

- **Syntax**

|        |                                                                   |
|:------:|-------------------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnBeforeTab**(row, col, oldRow, oldCol) { } |

- **Parameters**

|           |        |                   |
|:---------:|:------:|:-----------------:|
| Parameter |  Type  |       설 명       |
|    row    | number |    행의 Index     |
|    col    | number |   컬럼의 Index    |
|  oldRow   | number |  이전 행의 Index  |
|  oldCol   | number | 이전 컬럼의 Index |

- **Example**

```javascript
function mySheet_OnBeforeTab (row, col, oldRow, oldCol) {
console.log(“[OnBeforeTab] new : “ + row + “, ” + col + “, old : “ + oldRow + “, “ + oldCol);
}
```

- **제공 버전**

7.0.13.84