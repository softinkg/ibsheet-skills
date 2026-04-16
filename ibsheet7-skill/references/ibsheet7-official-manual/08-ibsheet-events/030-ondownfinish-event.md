# OnDownFinish Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnDownFinish Event

---

- **기능**

> 엑셀 및 텍스트 파일이 다운로드 완료 되었을때 이벤트가 발생한다.
>
> .

- **Syntax**

|        |                                                              |
|:------:|--------------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnDownFinish**(downloadType, result){} |

- **Parameters**

|              |         |                                               |
|:------------:|:-------:|:---------------------------------------------:|
|  Parameter   |  Type   |                     설 명                     |
| downloadType | String  |       엑셀/텍스트 종류. "EXCEL", "TEXT"       |
|    result    | Boolean | 다운로드 오류 여부. 성공 : true, 실패 : false |

- **Remarks**

- **Example**

```javascript
function mySheet_OnDownFinish(downloadType, result) {
alert(downloadType + ‘ 다운이 완료되었습니다. 다운로드 결과 : ‘ + result);
}
```

- **제공 버전**

7.0.0.0