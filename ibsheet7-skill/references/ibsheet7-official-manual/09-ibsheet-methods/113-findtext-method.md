# FindText Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > FindText Method

---

- **기능**

> 컬럼내에 특정 텍스트를 찾아서 행번호를 반환한다.
>
> 기본적으로 데이터 행 처음부터 끝까지 찾고자 하는 텍스트와 대소문자를 포함한 전체가 같은 것을 찾을수 있고, 인자의 설정에 따라 앞문자가 같은 데이터 행을 찾을 수 있다.
>
> 동일한 문자열을 컬럼에서 찾을수 없으면 –1을 반환한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 단위데이터 첫번째 행에 대해서 처리를 하고 SaveName으로 설정할 경우 해당 SaveName이 포함된 행에 대해서만 처리 한다.

- **Syntax**

|  |  |
|:--:|----|
| Syntax | ObjId.**FindText**(Col,SearchText,[StartRow],[FullMatch], [CaseSensitive]) |

- **Info**

> **Return**: Long, 찾아진 행번호 Default=-1

| Parameter     | Type            | 필수여부 | 설 명                          |
| ------------- | --------------- | ---- | ---------------------------- |
| Col           | Number / String | 필수   | 찾고자 하는 컬럼의 Index 또는 SaveName |
| SearchText    | String          | 필수   | 찾을 문자열                       |
| StartRow      | Number          | 선택   | 시작 행의 Index, Default="첫행"    |
| FullMatch     | Number          | 선택   | 글자 동일 종류, Default= -1        |
| CaseSensitive | Boolean         | 선택   | 대소문자 구분 여부, Default=1        |

> FullMatch 인자는 글자를 찾을 때 옵션으로 다음과 같이 처리된다.

|              |                                              |
|:------------:|:--------------------------------------------:|
| FullMatch 값 |                     기능                     |
|      -1      |    SearchText와 전체가 같은 행을 찾는다.     |
|      0       |   SearchText와 앞 부분이 같은 행을 찾는다.   |
|      1       |   SearchText와 뒤 부분이 같은 행을 찾는다.   |
|      2       | SearchText와 가운데 부분이 같은 행을 찾는다. |

- **Example**

```javascript
// 2컬럼내에 ‘한국'으로 시작하는 데이터의 행 위치 찾기
var Row1 = mySheet.FindText(2, "한국", 0, 0, 0);
//전체 글자가 "한국"인 데이터의 행 위치 찾기
var Row1 = mySheet.FindText(2, "한국", 0);
//뒤에 글자가 "은행"인 데이터의 행 위치 찾기
var Row1 = mySheet.FindText(2, "은행", 0, 1);
//글자 중에 "은"이라는 글자가 들어가는 행 위치 찾기
var Row1 = mySheet.FindText(2, "은", 0, 2);
//대소문자 구분하지 않고 찾기
var Row1 = mySheet.FindText(2, "Bank", 0, 2, 0);
```

- **제공 버전**

> **7.0.0.0**