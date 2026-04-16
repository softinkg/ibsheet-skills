# ShowCalendar Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ShowCalendar Method

---

- **기능**

> Text 타입의 컬럼에 포맷으로 날짜 포맷을 설정한 경우 OnClick 이벤트에서 ShowCalendar()를 실행하면 해당 컬럼 클릭 시 달력팝업을 출력해준다.
>
> 날짜 데이터형에 ‘0000-00-00', ‘2013-00-00' 형태의 데이터를 입력하고 싶은 경우 Text, Popup 컬럼에 CustomDate 속성을 1로 설정한 경우에도 OnClick, OnPopupClick 에서 사용 가능하다.
>
> CustomDate를 사용하는 경우 사용자 포맷을 지정해주어야 하며 년월일(####-##-##, \####/##/## 등), 년월(####-##, \####/## 등), 월일(##-##, \##/## 등) 타입이 가능하다.
>
> Format으로 지정한 \#의 갯수로 년월일(8개), 년월(6개), 월일(4개) 포맷이 결정된다.
>
> 년 포맷은 4자리 표기만 지원하고, 입출력 순서는 년월일 순서만 가능하다.
>
> 날짜 데이터값이 있는 경우 달력출력 시 해당날짜를 선택상태로 표시하며, 데이터가 없거나 날짜값이 아닌 경우 오늘 날짜를 선택상태로 출력해준다.

- **Syntax**

|        |                           |
|:------:|---------------------------|
| Syntax | ObjId. **ShowCalendar**() |

- **Info**

> **Return**: None

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

- **Example**

```javascript
// 텍스트 타입 컬럼 클릭시 달력 팝업 출력하기
function mySheet_OnClick(Row, Col) {
mySheet.ShowCalendar();
}
// Popup컬럼의 OnPopup 버튼 클릭시 달력 팝업 출력하기
function mySheet_OnPopupClick(Row,Col) {
mySheet.ShowCalendar();
}
```

- **제공 버전**

7.0.0.0