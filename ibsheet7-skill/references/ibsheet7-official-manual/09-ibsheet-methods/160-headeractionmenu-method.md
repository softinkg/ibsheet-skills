# HeaderActionMenu Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > HeaderActionMenu Method

---

- **기능**

> 헤더 컨텍스트 메뉴를 설정하거나 확인한다.
>
> SetConfig 또는 ibsheet.cfg 에서 UseHeaderActionMenu 를 1로 설정한 경우에만 사용 가능하다.
>
> UseHeaderActionMenu를 설정하고 SetHeaderActionMenu를 설정하지 않는경우 자동으로 기본 메뉴가 출력된다.
>
> MenuText, MenuCode를 "\|" 연산자로 조합한 문자열로 설정한다.
>
> MenuCode를 시트에서 제공하는 고정코드를 설정하는 경우 제품 내에서 해당 기능을 처리 한다.
>
> MenuText를 설정하지 않는 경우 기본메뉴로 설정처리 된다.

- **Syntax**

|        |     |                                 |
|:------:|:---:|---------------------------------|
| Syntax | Get | ObjId.**GetHeaderActionMenu**() |

- **Info**

> **Return**: Object, MenuText, MenuCode로 이루어진 객체

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```javascript
// 설정된 헤더메뉴 확인
var menu = mySheet.GetHeaderActionMenu();
console.log(menu.MenuText); // 설정된 MenuText 확인
console.log(menu.MenuCode); // 설정된 MenuCode 확인
```

- **Syntax**

|        |     |                                                   |
|:------:|:---:|---------------------------------------------------|
| Syntax | Set | ObjId.**SetHeaderActionMenu**(MenuText, MenuCode) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                                                                |
| --------- | ------ | ---- | ------------------------------------------------------------------ |
| MenuText  | String | 선택   | "\|" 문자로 연결한 메뉴명 문자열                                               |
| MenuCode  | String | 선택   | "\|" 문자로 연결한 메뉴코드 문자열. 시트에서 제공하는 고정 코드를 설정하는 경우 제품내에서 해당 기능을 처리한다. |

> \* 고정코드

|                      |                                                |
|:--------------------:|:----------------------------------------------:|
|         Code         |                     설 명                      |
|    _ibColSortAsc    |            대상 컬럼 오름 차순 정렬            |
|   _ibColSortDesc    |            대상 컬럼 내림 차순 정렬            |
|    _ibColHidden     |                대상 컬럼 숨김.                 |
| _ibCancelColHidden  |           헤더메뉴로 숨긴 컬럼 출력            |
| _ibSaveColPosition  | 현재 컬럼정보 저장 (위치, 컬럼 숨김여부, 너비) |
| _ibResetColPosition |              저장된 컬럼정보 삭제              |
|    _ibShowFilter    |                  필터행 출력                   |
|    _ibHideFilter    |                  필터행 숨김                   |

- **Example**

```
// aaa 메뉴 클릭시 필터를 출력하고, bbb 메뉴 클릭시 필터를 숨기는 헤더 메뉴를 설정한다.
mySheet.SetHeaderActionMenu("aaa|*-|bbb", "_ibShowFilter||_ibHideFilter");
```

- **제공 버전**

| **7.0.0.0**  |                                                |
|:------------:|------------------------------------------------|
| **7.0.13.6** | _ibColSortAsc, _ibColSortDesc 고정 코드 추가 |