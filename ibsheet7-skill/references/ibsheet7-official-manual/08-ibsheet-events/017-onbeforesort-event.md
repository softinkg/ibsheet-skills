# ### OnBeforeSort Event

> **IBSheet7 개발자 가이드** > IBSheet Events > ### OnBeforeSort Event

---

- **기능**

> Sort 이벤트가 발생되기 전에 발생하는 이벤트

- **Syntax**

|        |                                               |
|:------:|-----------------------------------------------|
| Syntax | **function 오브젝트ID_OnBeforeSort**(col) { } |

- **Parameters**

|           |      |                              |
|:---------:|:----:|:----------------------------:|
| Parameter | Type |            설 명             |
|    col    | Int  | Sort 선택한 컬럼 인덱스 확인 |

- **Remarks**

> 헤더 클릭시 소트이벤트 발생전에 호출된다.  
> 소트수행전 대기이미지 호출등에 활용된다.

- **Example**

```javascript
function mySheet_OnBeforeSort(col) {
console.log(“SortColumn : “ + col);
}
```

- **제공 버전**

7.0.13.75