# EtcData Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > EtcData Method

---

- **기능**

> 데이터 정보 이외의 정보를 확인하거나 설정한다.
>
> 이 속성은 조회 함수를 이용하여 조회 결과 또는 저장 처리 결과에서 추가 정보를 조회 한 경우 기타 정보로 저장할 수 있다.
>
> 기타 정보는 키 이름과 키 값으로 구성 되며 속성을 바로 설정하거나 확인할 수 있다.
>
> XML 포맷인 경우는 <ETC-DATA> 태그를 사용하며 다음과 같이 사용한다.

| 기본 구조 | **** 키값** 홍길동** 30**** ****                                        |
| ----- | ------------------------------------------------------------------ |
| 조회 시  | 태그와  태그 사이에 설정한다. 예) **** 홍길동 30 **** CWOF-171 17평 2040000 2101200 |
| 저장 시  | 태그와  태그 사이에 설정한다. 예) **** 홍길동 30 **"                               |

> JSON 포맷인 경우는 etc 키를 사용하며 다음과 같이 사용한다.

| 기본 구조 | **etc**:{ "키이름":"키값", name: "홍길동", age: 30}                                 |
| ----- | --------------------------------------------------------------------------- |
| 조회 시  | 예) { etc:{ name: "홍길동", age: 30}, data:[ {C1: "CWOF-171", C2: "17평"}, … ] } |
| 저장 시  | 예) { etc:{ name: "홍길동", age: 30}, result:[ {Code:0, Message: "저장성공"}, … ] } |

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Get | ObjId.**GetEtcData**(KeyName) |

- **Info**

> **Return**: String, 키에 설정된 값 (Get Method 인 경우)

| Parameter | Type   | 필수여부 | 설 명       |
| --------- | ------ | ---- | --------- |
| KeyName   | String | 필수   | 기타정보 키 이름 |

- **Example**

```javascript
// XML을 통해서 조회된 기타 정보를 TextBox에 설정한다.
document.form1.txtAge.value = mySheet.GetEtcData("age")
// 저장 처리 완료 후 기타 정보를 이용하여 페이지를 이동한다.
mySheet.DoSave("save.html");
location.href = "/site/showmaster.html?keyinfo=" + mySheet.GetEtcData("전표번호")
```

**  **

- **Syntax**

|        |     |                                      |
|:------:|:---:|--------------------------------------|
| Syntax | Set | ObjId.**SetEtcData**(KeyName, Value) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명       |
| --------- | ------ | ---- | --------- |
| KeyName   | String | 필수   | 기타정보 키 이름 |
| Value     | String | 필수   | 기타정보 키 값  |

- **Example**

```
// 기타 정보의 값을 변경한다.
mySheet.SetEtcData("age", 40);
// 새로운 기타정보를 생성한다.
mySheet.SetEtcData("Pay", 2000000);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **