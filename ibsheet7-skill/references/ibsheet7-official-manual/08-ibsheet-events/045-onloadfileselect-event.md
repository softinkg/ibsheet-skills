# OnLoadFileSelect Event

> **IBSheet7 개발자 가이드** > IBSheet Events > OnLoadFileSelect Event

---

- **기능**

> Excel, Text 로드시 파일 선택시 이벤트가 발생한다.

- **Syntax**

|        |                                                              |
|:------:|--------------------------------------------------------------|
| Syntax | **function 오브젝트ID_OnLoadFileSelect**(from, fileName) { } |

- **Parameters**

|           |        |                     |
|:---------:|:------:|:-------------------:|
| Parameter |  Type  |        설 명        |
|   From    | String |  엑셀, 텍스트 구분  |
| FileName  | String | 파일경로 및 파일 명 |

- **Example**

```javascript
function mySheet_OnLoadFileSelect(from, fileName) {
if(from == “Excel”) {
console.log(from + "파일이 선택되었습니다. 경로 : " + filename);
} else if (from == “TEXT”) {
console.log(from + "파일이 선택되었습니다. 경로 : " + filename);
}
}
```

- **제공 버전**

| **7.0.0.0** |     |
|-------------|-----|