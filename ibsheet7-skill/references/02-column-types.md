# 컬럼 타입 레퍼런스

IBSheet7은 21개의 컬럼 타입을 지원합니다.

---

## Status (상태 표시)
행의 상태(I:입력, U:수정, D:삭제)를 표시합니다.
```javascript
{Header:"상태", Type:"Status", SaveName:"STATUS", Align:"Center", Width:60}
```

## DelCheck (삭제 체크)
체크하면 해당 행의 상태(Status)가 D:삭제 로 변경되고, 행의 Edit가 불가능해 집니다.
```javascript
{Header:"삭제", Type:"DelCheck", SaveName:"DEL_CHK", Width:50}
```

## Seq (순번)
자동 순번을 표시합니다. 저장 대상이 아닙니다.
```javascript
{Header:"NO", Type:"Seq", SaveName:"SEQ", Align:"Center", Width:40}
```

## Text (문자열)
일반 텍스트 입력/표시 컬럼입니다.
```javascript
{Header:"이름", Type:"Text", SaveName:"NAME", Width:100, KeyField:1, MultiLineText:1}

// 포맷 사용: 주민번호, 전화번호 등
{Header:"전화번호", Type:"Text", SaveName:"PHONE", Format:"PhoneNo"}
{Header:"주민번호", Type:"Text", SaveName:"IDNO", Format:["######-#******","###-**-**###"]}
{Header:"우편번호", Type:"Text", SaveName:"POST", Format:"PostNo"}
{Header:"카드번호", Type:"Text", SaveName:"CARD", Format:"CardNo"}
{Header:"사용자 정의", Type:"Text", SaveName:"CUSTOM", Format:"###-**-**###"}
```

## Int (정수)
정수 입력 컬럼입니다.
```javascript
{Header:"수량", Type:"Int", SaveName:"QTY", Format:"Integer", Align:"Right", Width:70}
{Header:"가격", Type:"Int", SaveName:"PRICE", Format:"#,###만원", Align:"Center"}
{Header:"연식", Type:"Int", SaveName:"YEAR", Format:"####년", Align:"Center"}
```

## Float (실수)
실수 입력 컬럼입니다.
```javascript
{Header:"실수", Type:"Float", SaveName:"FLOAT_DATA", Format:"#,##0.00", Align:"Right"}
```

## Date (날짜)
날짜 선택/입력 컬럼입니다.
```javascript
{Header:"날짜", Type:"Date", SaveName:"DATE", Format:"Ymd", Align:"Center", Width:110}
{Header:"시간", Type:"Date", SaveName:"TIME", Format:"Hm", Align:"Center"}

// 시작/종료 날짜 연동
{Header:"시작일", Type:"Date", SaveName:"START", Format:"Ymd", EndDateCol:"END"}
{Header:"종료일", Type:"Date", SaveName:"END", Format:"Ymd", StartDateCol:"START"}
```

## Combo (드롭다운)
드롭다운 선택 컬럼입니다.
```javascript
{Header:"상태", Type:"Combo", SaveName:"STATUS",
  ComboText:"대기|진행중|완료", ComboCode:"01|02|03"}
```

## ComboEdit (편집가능 콤보)
직접 입력도 가능한 콤보 컬럼입니다.
```javascript
{Header:"학교", Type:"ComboEdit", SaveName:"SCHOOL",
  ComboText:"고려대학교|서울대학교|연세대학교",
  ComboCode:"AA|BB|CC", Validation:1}

// ShowCol 속성으로 코드|텍스트 함께 표시
{Header:"코드", Type:"ComboEdit", SaveName:"CODE",
  ComboText:"WG010\t진입도로|WG020\t구내운반", ComboCode:"WG010|WG020", ShowCol:1}
```

## CheckBox (체크박스)
단일 또는 다중 체크박스입니다.
```javascript
// 단일 체크 (기본값 1:check, 0:uncheck)
{Header:"선택", Type:"CheckBox", SaveName:"CHK", Align:"Center",
  TrueValue:"Y", FalseValue:"N"}

// 다중 체크 (ItemText/ItemCode)
{Header:"항목", Type:"CheckBox", SaveName:"MULTI_CHK",
  ItemText:"입금|출금|이체", ItemCode:"H|M|L", RadioIcon:1,
  DefaultValue:"M:1|L:1"}
```

## DummyCheck (더미 체크박스)
저장 대상이 아닌 체크박스입니다. 주로 UI 선택용.
```javascript
{Header:"선택", Type:"DummyCheck", SaveName:"CHK"}
```

## Radio (라디오 버튼)
라디오 버튼 컬럼입니다.
```javascript
{Header:"선택", Type:"Radio", SaveName:"RADIO", Width:50}
```

## AutoSum (자동 합계)
값 변경 시 자동으로 합계를 계산합니다. 합계는 데이터 영역 하단에 합계행에 표시됩니다.
```javascript
{Header:"금액", Type:"AutoSum", SaveName:"AMT", Format:"#,###", Align:"Right"}

// CalcLogic으로 수식 지정 (|컬럼명| 으로 참조)
{Header:"합계", Type:"AutoSum", SaveName:"TOTAL", Format:"#,##0.00",
  CalcLogic:"|AMT1|+|AMT2|"}

// 함수형 CalcLogic
{Header:"매출", Type:"AutoSum", SaveName:"SALE", CalcLogic:{
  TriggerCol:"PRICE|QTY",
  Function: function(calInfo) {
    var price = calInfo.Sheet.GetCellValue(calInfo.Row, "PRICE");
    var qty = calInfo.Sheet.GetCellValue(calInfo.Row, "QTY");
    return price * qty;
  }
}}

// AutoSum type 대신 AutoSum 속성과 SumType 속성으로 합계 유형 변경
{Header:"평균", Type:"Float", SaveName:"AVG", AutoSum: 1, SumType:"Avg"}

// ZeroToReplaceChar: 0값 대체 문자
{Header:"합계", Type:"AutoSum", SaveName:"SUM", ZeroToReplaceChar:"-"}

// MaximumValue: 최대값 입력 제한
{Header:"합계", Type:"AutoSum", SaveName:"SUM", MaximumValue:10000}
```

## AutoAvg (자동 평균)
값 변경 시 자동으로 평균을 계산합니다.
```javascript
{Header:"추천수", Type:"AutoAvg", SaveName:"RCMN", Format:"#,###"}
```

## Button (버튼)
클릭 가능한 버튼 컬럼입니다.
```javascript
{Header:"상세", Type:"Button", SaveName:"BTN", DefaultValue:"상세정보",
  Width:100, Align:"Center", Cursor:"Default"}
// 클릭 이벤트: mySheet_OnButtonClick(Row, Col)
```

## Popup (팝업)
텍스트 오른쪽에 팝업 버튼이 있는 컬럼입니다. 직접 편집 불가.
```javascript
{Header:"팝업", Type:"Popup", SaveName:"POPUP", PopupCheckEdit:0}
// 클릭 이벤트: mySheet_OnPopupClick(Row, Col)
```

## PopupEdit (팝업 편집)
텍스트 오른쪽에 팝업 버튼이 있고 직접 편집도 가능한 컬럼입니다.
```javascript
{Header:"팝업", Type:"PopupEdit", SaveName:"POPUP", Width:120, PopupAlign:"Left"}
```

### Text + PopupButton 조합
```javascript
// Text 타입에 팝업 버튼 추가
{Header:"팝업에디트", Type:"Text", PopupButton:1, Width:120, SaveName:"CURRENCY", PopupAlign:"Left"}
```

## Image (이미지)
이미지를 표시하는 컬럼입니다.
```javascript
{Header:"이미지", Type:"Image", SaveName:"IMG", Align:"Center",
  ImgWidth:60, ImgHeight:60}

// SetImageList로 이미지 등록
mySheet.SetImageList(0, "img/image1.jpg");
mySheet.SetImageList(1, "img/image2.jpg");
```

## Pass (패스워드)
비밀번호 마스킹 컬럼입니다.
```javascript
{Header:"비밀번호", Type:"Pass", SaveName:"PWD", Width:70}
```

## Html (HTML)
HTML 태그를 렌더링하는 컬럼입니다.
```javascript
{Header:"내용", Type:"Html", SaveName:"HTML_COL", Width:80, Align:"Center"}
```

## Tree (트리)
트리 구조를 표시하는 컬럼입니다. TreeCol 속성으로 지정합니다.
```javascript
{Header:"부서", Type:"Text", SaveName:"DEPT", TreeCol:1, Width:250,
  LevelSaveName:"TREELEVEL", TreeCheck:1, CheckSaveName:"TCheck", Edit:0}
```

---

## 예제: 모든 데이터 타입 종합

> 출처: `docs/examples/01/datatype.html`

```javascript
function LoadPage() {
  mySheet.UseEditMask = 1;
  var initSheet = {};
  initSheet.Cfg = {ToolTip:1, FrozenCol:0};
  initSheet.HeaderMode = {Sort:1, ColMove:1, ColResize:1, HeaderCheck:1};
  initSheet.Cols = [
    {Header:"NO", Type:"Seq", Align:"Center", SaveName:"seq", Width:40},
    {Header:"상태", Type:"Status", Align:"Center", SaveName:"sStatus", Width:40},
    {Header:"삭제", Type:"DelCheck", Width:50},
    {Header:"문자열", Type:"Text", SaveName:"TEXT_DATA", MultiLineText:1, KeyField:1, Width:80},
    {Header:"콤보", Type:"Combo", Width:70, SaveName:"COMBO_DATA",
      ComboText:"대기|진행중|완료", ComboCode:"01|02|03", PopupText:"대기|진행중|완료"},
    {Header:"콤보에디트", Type:"ComboEdit", Width:80, SaveName:"COMBOEDIT_DATA",
      ComboText:"고려대학교|국민대학교|서울대학교|연세대학교",
      ComboCode:"AA|BB|CC|FF", Validation:1},
    {Header:"팝업", Type:"Popup", Width:70, SaveName:"ISO", PopupCheckEdit:0},
    {Header:"팝업에디트", Type:"Text", PopupButton:1, Width:120, SaveName:"CURRENCY", PopupAlign:"Left"},
    {Header:"자동합계", Type:"AutoSum", SaveName:"AUTOSUM_DATA", Width:70, Format:"#,###",
      ZeroToReplaceChar:"", MaximumValue:10000},
    {Header:"자동평균", Type:"AutoSum", Align:"Right", SaveName:"AUTOAVG_DATA", Width:70,
      Format:"Integer", SumType:"Avg"},
    {Header:"정수", Type:"Int", Align:"Right", SaveName:"INT_DATA", Format:"Integer", Width:70},
    {Header:"실수", Type:"Float", Align:"Right", SaveName:"FLOAT_DATA", Format:"#,##0.00", Width:70},
    {Header:"날짜", Type:"Date", Align:"Center", SaveName:"DATE_DATA", Format:"Ymd", Width:110},
    {Header:"주민/사업자번호", Type:"Text", Align:"Center", SaveName:"IDNO",
      Format:["######-#******","###-**-**###"], Width:120},
    {Header:"우편번호", Type:"Text", Align:"Center", SaveName:"POSTNO", Format:"PostNo", Width:70},
    {Header:"카드번호", Type:"Text", Align:"Center", SaveName:"CARDNO", Format:"CardNo", Width:150},
    {Header:"전화번호", Type:"Text", Align:"Center", SaveName:"PHONENO", Format:"PhoneNo", Width:120},
    {Header:"사용자 정의 포멧", Type:"Text", Align:"Center", SaveName:"USERFORMAT",
      Format:"###-**-**###", Width:100},
    {Header:"이미지", Type:"Image", Align:"Center", SaveName:"IMAGE_DATA", Width:70},
    {Header:"패스워드", Type:"Pass", SaveName:"PASS_DATA", Width:70},
    {Header:"버튼", Type:"Button", SaveName:"BUTTON", DefaultValue:"상세정보",
      Width:100, Align:"Center", Cursor:"Default"},
    {Header:"다중체크박스", Type:"CheckBox", SaveName:"MULTICHECKBOX_DATA", Width:170,
      ItemText:"입금|출금|이체", ItemCode:"H|M|L", RadioIcon:1, DefaultValue:"M:1|L:1"},
    {Header:"체크박스", Type:"DummyCheck", SaveName:"CHECKBOX_DATA", Width:50,
      PopupText:"true|false"},
    {Header:"라디오", Type:"Radio", SaveName:"RADIO_DATA", Width:50}
  ];
  IBS_InitSheet(mySheet, initSheet);

  mySheet.SetShowButtonImage(2);
  mySheet.SetClipPasteMode(2);
  mySheet.SetImageList(0, "img/am.jpg");
  mySheet.SetImageList(1, "img/ca.jpg");
  mySheet.SetDataLinkMouse("AUTOSUM_DATA", 1);
  mySheet.SetComboOpenMode(1);
}
```

### 버튼/팝업 이벤트 처리
```javascript
function mySheet_OnButtonClick(Row, Col) {
  alert(Row + "행의 버튼이 클릭되었습니다.");
}

function mySheet_OnPopupClick(Row, Col) {
  var v = mySheet.GetCellText(Row, "ISO");
  document.getElementById("popupFrame").src = "./popup.jsp?searchCondition=" + encodeURIComponent(v);
}
```
