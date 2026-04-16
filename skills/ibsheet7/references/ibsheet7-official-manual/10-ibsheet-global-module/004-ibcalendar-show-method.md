# IBCalendar.Show Method

> **IBSheet7 개발자 가이드** > IBSheet Global Module > IBCalendar.Show Method

---

- **기능**

> 달력 팝업을 외부의 컨트롤에서 사용하도록 설정한다
>
> 일반적으로 CallBack 함수를 지정하는 경우 첫번째 인자로 선택한 날짜 문자열이 전달되며, 그 외 CallBack 함수로 전달하고자 하는 인자가 있는 경우 CallBackParam 을 설정한다. CallBackParam으로 설정된 객체는 CallBack 함수의 두번째 인자로 전달된다.

- **Syntax**

|        |                                |
|:------:|--------------------------------|
| Syntax | **IBCalendar.Show**(val, obj); |

- **Info**

> **Return**: String, (달력 팝업 Dialog에서 선택한 날짜값)

| Parameter | Type   | 필수여부 | 설 명                   |
| --------- | ------ | ---- | --------------------- |
| val       | String | 필수   | 날짜데이터값 (Default=현재날짜) |
| obj       | Object | 선택   | 기능을 json 형태로 설정한다.    |

> **세부내용**
>
> 컬럼별로 설정 할 수 있는 속성은 다음과 같다.

| 속성             | 타입                | 설명                                                                                                                                                                                                                                                                      |
| -------------- | ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| CalButtonAlign | String            | 달력팝업에서 버튼을 사용하는 경우 정렬방법을 설정 \| 설정값    \| 내용          \| \| ------ \| ----------- \| \| Left   \| 왼쪽정렬        \| \| Center \| 가운데정렬 (기본값) \| \| Right  \| 오른쪽정렬       \|                                                                                                 |
| CalButtons     | String            | 달력팝업의 사용할 버튼 설정 사용하고자 하는 버튼을 "\|" 로 연결하여 설정한다. \| 설정값        \| 내용         \| \| ---------- \| ---------- \| \| Close      \| 취소 버튼      \| \| Today      \| 오늘일자 입력 버튼 \| \| Yesterday  \| 어제일자 입력 버튼 \| \| InputEmpty \| 빈값 입력 버튼   \| \| Ok         \| 선택 버튼      \| |
| CallBack       | String / Function | allBack함 수명 또는 함수 객체                                                                                                                                                                                                                                                    |
| CallBackParam  | Object            | CallBack 함수에서 받을 인자 객체                                                                                                                                                                                                                                                  |
| Format         | String            | 날짜포맷 패턴(Default="yyyy/MM/dd")                                                                                                                                                                                                                                           |
| Holiday        | String            | 달력에 표시할 사용자 정의 휴일 설정 파이프 연산자로 설정값을 연결한 문자열로 설정 할 수 있으며 포맷은 yyyyMMdd 만 허용한다. 매년, 매월에 대한 와일드카드로 * 을 사용한다. **설정 예)** Holiday : "20120725\|*0703\|2012*27\|**17" *0703 : 매년 7월 3일 2012*27 : 2012년 매월 27일 **17 : 매년, 매월 17일                                                  |
| Result         | Object            | 선택 결과를 설정할 객체 (input 객체)                                                                                                                                                                                                                                                |
| ShowYM         | Boolean           | 년월 선택화면 우선 표시 여부                                                                                                                                                                                                                                                        |
| Target         | String / Object   | "Mouse" (마지막 마우스 위치 사용시, Default) 또는 달력 버튼 Object (달력 버튼 위치 사용시)                                                                                                                                                                                                        |
| X              | Number            | (좌표값 사용시), X 축 좌표값                                                                                                                                                                                                                                                      |
| Y              | Number            | (좌표값 사용시), Y 축 좌표값                                                                                                                                                                                                                                                      |

- **Example**

```javascript
// 날짜데이터값 입력
var val = document.getElementById("DateText").value;
// 달력 팝업 Dialog 위치 : X, Y 좌표값 사용시
var obj = { Format:"yyyy/MM/dd", X:300, Y:600, CallBack:"Test" };
// 달력 팝업 Dialog 위치 : 마우스 마지막 위치 사용시
var obj = { Format:"yyyy/MM/dd", Target:"Mouse", CallBack: "Test" };
// 달력 팝업 Dialog 위치 : 달력 버튼 위치 사용시
var obj = { Target:document.getElementById("DateBtn"), CallBack: "Test" };
// CalButtons 속성 : 달력 닫기 버튼 옵션 설정 사용시
var obj = { Format:"Ymd", Target:document.getElementById("DateBtn"), CallBack: "Test" , CalButtons : "Close"};
// 달력 닫기 버튼 옵션 설정 사용시 정렬 설정: 왼쪽 정렬
var obj = { Format:"Ymd", Target:document.getElementById("DateBtn"), CallBack: "Test", CalButtons : "Close", CalButtonAlign : "Left" };
// 사용자 정의 휴일 설정
var obj = { Format:"Ymd", Target:document.getElementById("DateBtn"), CallBack: "Test", Holiday: " 20101215|*1203"};
// 달력 출력
IBCalendar.Show("20140415", obj);
// fnName : 함수명으로 function 생성
function Test (date){
// 달력 팝업 Dialog서 날짜 선택시 리턴값
document.getElementById("DateText").value = date;
}
```

- **제공 버전**

|  **7.0.0.0**  |                                        |
|:-------------:|----------------------------------------|
| **7.0.11.0**  | CalButtons 속성의 "InputEmpty" 값 추가 |
| **7.0.13.10** | CalButtons 속성의 "Ok" 값 추가         |
| **7.0.13.16** | ShowYM 속성 추가                       |