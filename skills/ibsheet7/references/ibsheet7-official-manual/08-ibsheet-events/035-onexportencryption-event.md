# OnExportEncryption Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnExportEncryption Event

---

- **기능**

> 시트의 데이터를 엑셀 또는 텍스트 파일로 변환시 각 셀에 대한 데이터 수집시 발생하는 이벤트 이다. 해당 셀의 데이터에 대한 암호화 또는 마스킹 처리를 하는 경우 이 이벤트를 이용하여 처리 한다. 이 이벤트에서 반환값이 있는 경우 해당 셀의 데이터는 반환한 값으로 치환되어 처리 된다.
>
> *\* 해당 이벤트는 PDF 문서변환은 지원하지 않는다.*

- **Syntax**

| Syntax | **function 오브젝트ID_OnExportEncryption(Row, Col,** **SaveName, Value) { }** |
| ------ | ------------------------------------------------------------------------- |

- **Parameters**

|           |        |                  |
|:---------:|:------:|:----------------:|
| Parameter |  Type  |      Remark      |
|    Row    |  Long  |  셀의 Row Index  |
|    Col    |  Long  |  셀의 Col Index  |
| SaveName  | String | 컬럼의 SaveName  |
|   Value   | String | 셀의 현재 데이터 |

- **Example**

```javascript
function mySheet_OnExportEncryption(Row, Col, SaveName, Value){
var val = Value;
// SaveName 이 sName 인 경우 마지막 문자열을 *로 치환한다.
If (SaveName == "sName") {
val = val.substring(0, val.length – 1) + "*";
return val;
}
}
```

- **제공 버전**

| **7.0.13.2** |     |
|--------------|-----|