# OnRowSearchEnd Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnRowSearchEnd Event

---

- **기능**

> DoSearch나 LoadSearchData 메서드를 통해 데이터가 조회되는 과정에서 행단위로 발생한다.
>
> 특정 행의 데이터를 기준으로 판단하여 Cell에 색상이나 배경색등을 표현하고자 하는 경우 유용하게 쓰일수 있다.
>
> 이 기능은 조회 중에 행단위로 한번씩 발생함으로 이벤트 안에 로직이 복잡하거나 loop문이 들어가는 경우 조회속도가 저하될 수 있다.

- **Syntax**

|        |                                                  |
|:------:|--------------------------------------------------|
| Syntax | **function 오브젝트ID_OnRowSearchEnd** (row) { } |

- **Parameters**

|           |         |             |
|:---------:|:-------:|:-----------:|
| Parameter |  Type   |    설 명    |
|    row    | Integer | 행의 인덱스 |

- **Example**

```javascript
function mySheet_OnRowSearchEnd(row) {
//3번컬럼이 check되어있고, 4번 컬럼의 값이 100보다 클때, 6번 컬럼의 글자 색상을 붉은색으로 변경한다.
If( mySheet.GetCellValue(row,3) == 1 && mySheet.GetCellValue(row,4) > 100){
mySheet.SetCellFontColor(row ,6 ,"#FF0000");
}
}
```

- **제공 버전**

7.0.0.0