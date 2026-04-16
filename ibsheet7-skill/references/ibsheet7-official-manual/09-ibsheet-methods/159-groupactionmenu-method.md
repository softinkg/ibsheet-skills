# GroupActionMenu Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GroupActionMenu Method

---

- **기능**

> 그룹행 영역에 설정된 컨텍스트 메뉴를 설정하거나 확인 한다.
>
> 이 기능을 사용하려면 초기화 함수(SetConfig)설정시 UseGroupActionMenu:1 로 설정되어야 한다.
>
> MenuText, MenuCode를 "\|" 연산자로 조합한 문자열로 설정한다.
>
> MenuCode 인자 설정시 사전 정의 코드를 사용하는 경우 별도 코드 작성없이 해당 기능이 처리되고, 그렇지 않은 경우에는 OnSelectMenu 이벤트에서 처리할 수 있다.
>
> MenuText를 설정하지 않는 경우 기본메뉴로 설정처리 된다.

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Get | ObjId.**GetGroupActionMenu**() |

- **Info**

> **Return**: Object, MenuText, MenuCode로 이루어진 객체

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 그룹행의 컨텍스트 메뉴 확인
console.log("groupMenu:", mySheet.GetGroupActionMenu());
```

- **Syntax**

|        |     |                                                  |
|:------:|:---:|--------------------------------------------------|
| Syntax | Set | ObjId.**SetGroupActionMenu**(MenuText, MenuCode) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명 |                         |
| --------- | ------ | ---- | --- | ----------------------- |
| MenuText  | String | 필수   |     | 메뉴명을 구분자 "\|"로 연결한 문자열  |
| MenuCode  | String | 필수   |     | 메뉴코드를 구분자 "\|"로 연결한 문자열 |

> 기본으로 제공되는 사전 정의 코드는 아래와 같다.

|                    |                     |
|:------------------:|:-------------------:|
|        Code        |        기능         |
| _ibInitGroupCols  |  그룹 정보 초기화   |
| _ibSaveGroupCols  |   그룹 정보 저장    |
| _ibResetGroupCols | 그룹 정보 저장 취소 |

- **Example**

```
//컬럼 저장 메뉴 구성
mySheet.SetGroupActionMenu("그룹 저장|그룹 저장 취소", "_ibSaveGroupCols|_ibResetGroupCols");
```

- **제공 버전**

| **7.0.13.40** |     |
|---------------|-----|