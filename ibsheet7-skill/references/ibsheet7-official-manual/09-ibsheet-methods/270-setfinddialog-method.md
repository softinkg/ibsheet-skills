# SetFindDialog Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SetFindDialog Method

---

- **기능**

> 단축키 Ctrl+Shift+F 를 이용한 찾기 다이얼로그의 기본 정보를 설정 한다.
>
> FullMatch 인자는 찾기 종류 항목을 설정 한다. FindText Method의 FullMatch 설정과 동일 하며 설정값은 아래와 같다.

|              |                                              |
|:------------:|:--------------------------------------------:|
| FullMatch 값 |                     기능                     |
|      -1      |    SearchText와 전체가 같은 행을 찾는다.     |
|      0       |   SearchText와 앞 부분이 같은 행을 찾는다.   |
|      1       |   SearchText와 뒤 부분이 같은 행을 찾는다.   |
|      2       | SearchText와 가운데 부분이 같은 행을 찾는다. |

- **Syntax**

|  |  |
|:--:|----|
| Syntax | ObjId.**SetFindDialog**(Show,[Col],[FullMatch],[FirstStart],[CaseSensitive], [KeepDialog], [FindWrap]) |

- **Info**

> **Return**: None.

| Parameter     | Type        | 필수여부 | 설 명                                               |
| ------------- | ----------- | ---- | ------------------------------------------------- |
| Show          | Boolean     | 필수   | 찾기 다이얼로그 사용 여부                                    |
| Col           | Long/String | 선택   | 찾을 컬럼의 Index 또는 SaveName 빈값인 경우 전체 컬럼, Default="" |
| FullMatch     | Integer     | 선택   | 텍스트 일치 종류 설정, Default=-1                          |
| FirstStart    | Boolean     | 선택   | 시작 위치 설정, Default=1                               |
| CaseSensitive | Boolean     | 선택   | 대소 구분 설정, Default=0                               |
| KeepDialog    | Boolean     | 선택   | 찾기 후 창 닫기 여부 설정, Default=0                        |
| FindWrap      | Boolean     | 선택   | 끝에서 되돌리기 여부 설정, Default =0                        |

- **Example**

```
//찾기창 사용, 대상 컬럼:5, 시작위치:포커스행 다음, 일치종류:가운데일치
mySheet.SetFindDialog(1, 5, 2, 0);
```

- **제공 버전**

|  **7.0.0.0**   |                     |
|:--------------:|---------------------|
| **7.0.13.146** | FindWrap 인자 추가. |