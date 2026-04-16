# OnTreeChild Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnTreeChild Event

---

- **기능**

> 자식을 조회하지 않은 상태에서 부모 노드에서 트리 확장기능을 선택했을 때 이벤트가 발생한다.
>
> 이벤트가 발생하는 자식노드를 DoSearchChild 조회함수로 조회하는 기능을 처리할수 있다.
>
> 이 이벤트는 조회시 XML 파일에는 <TR HAVECHILD="1">, JSON파일에는 TR 에 HaveChild 인자값을 먼저 설정하도록 한다.
>
> HaveChild 속성값을 설정한 데이터에서만 발생하므로 반드시 조회XML,JSON 생성시 자식 레벨이 있는지 설정하여 처리하도록 한다.
>
> 이 이벤트는 트리 형태 데이터를 한꺼번에 조회하지 않고, 트리 확장 버튼을 눌렀을 때 자식 레벨의 데이터를 조회하기 위한 용도로 사용된다.

- **Syntax**

|        |                                          |
|:------:|------------------------------------------|
| Syntax | **function 오브젝트ID_OnTreeChild**(Row) |

- **Parameters**

|           |      |                        |
|:---------:|:----:|:----------------------:|
| Parameter | Type |         설 명          |
|    Row    | Long | 확장할 부모 행의 Index |

- **Example**

```javascript
// 자식데이터 조회하기
<script type="text/Javascript">
function mySheet_OnTreeChild(Row){
var url = "";
// 4컬럼 : 트리컬럼
switch(mySheet.GetCellValue(Row, 4)){
case "서울" :
url = " type15_dat(1).xml";
break;
case "인천":

url = "type15_data(2).xml";
break;
}
mySheet.DoSearchChild(Row, url, "", 1);
}
</script>
```

- **제공 버전**

7.0.0.0