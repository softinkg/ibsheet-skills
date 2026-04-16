# 헬퍼 함수 및 팁

## 폼 연동 헬퍼 함수

### IBS_CopyJson2Form
JSON 데이터를 Form에 매핑합니다.
```javascript
IBS_CopyJson2Form({"formName": jsonData}, document.formName);
```

### FormQueryString
Form 데이터를 QueryString으로 생성합니다.
```javascript
FormQueryString(formObj);
```

### IBS_CopyForm2Sheet
Form 데이터를 시트에 복사합니다.
```javascript
IBS_CopyForm2Sheet(formObj, sheetObj);
```

### IBS_CopySheet2Form
시트 데이터를 Form에 복사합니다.
```javascript
IBS_CopySheet2Form(sheetObj, formObj);
```

---

## 시트 설정 메서드

### 편집 관련
```javascript
mySheet.SetEditableColorDiff(0);  // 0:없음, 1:차이표시, 2:읽기전용 강조
mySheet.SetEditable(1);            // 편집 가능/불가
mySheet.SetFocusEditMode(1);       // 포커스 편집 모드
```

### 우클릭 메뉴
```javascript
mySheet.SetActionMenu("메뉴1|메뉴2|메뉴3");
```

### 붙여넣기 모드
```javascript
mySheet.SetClipPasteMode(mode);
// 0:한셀에(기본), 1:구분자기준, 2:모자란부분추가, 3:전체
```

### 콤보
```javascript
mySheet.SetComboOpenMode(1);  // 콤보 즉시 펼침
```

### 데이터
```javascript
mySheet.SetDataAutoTrim(1);   // 데이터 자동 트림
```

### 스크롤 정보
```javascript
mySheet.SetScrollInfoFormat("데이터 로딩 중...");
mySheet.SetScrollInfoFormat("[TOPROW / TOTALROWS] <font color='blue'>|MOVIE_NM|</font>");
```

### 편집 동작
```javascript
mySheet.SetEditArrowBehavior(0);  // 편집시 방향키 동작
```

### 렌더링 제어
```javascript
mySheet.RenderSheet(0);  // 렌더링 중지
mySheet.RenderSheet(1);  // 렌더링 재개
```

### 대기 이미지
```javascript
mySheet.WaitImageVisible = 0;  // 숨김
```

### 메시지 모드
```javascript
mySheet.SetShowMsgMode(0);  // 메시지 숨김
mySheet.SetShowMsgMode(1);  // 메시지 표시
```

### 선택 모드
```javascript
mySheet.SetSelectionMode(mode);
```

### 버튼 이미지
```javascript
mySheet.SetShowButtonImage(2);
```

### 헤더 매핑 하이라이트
```javascript
mySheet.SetClickHeaderMapping(1);
mySheet.SetClickHeaderMappingColor('#665577');
```

### 건수 정보
```javascript
mySheet.SetCountInfoElement(document.getElementById('totalCount'));  // 외부 표시
mySheet.SetCountPosition(4);                                         // 위치 설정
```

### 이미지
```javascript
mySheet.SetImageList(index, "imgPath");
```

### 순번/정렬
```javascript
mySheet.ReNumberSeq();   // 순번 재매기기
mySheet.ColumnSort();     // 정렬
```

### 합계행
```javascript
mySheet.SetSumValue(0, "SaveName", "합 계");
mySheet.SetSumValue(0, "표시할 텍스트");
```

### 테마
```javascript
mySheet.ThemeVersion = 1;
mySheet.SetTheme("GY2", "Gray2");
```

### 마우스 데이터 링크
```javascript
mySheet.SetDataLinkMouse("SaveName", 1);
```

### 셀 콤보/속성 변경
```javascript
mySheet.CellComboItem(row, "SaveName", {ComboText:"A|B", ComboCode:"1|2"});
mySheet.InitCellProperty(row, "SaveName", {Type:"CheckBox", ItemText:"가|나|다", ItemCode:"A|B|C"});
```

### 페이징
```javascript
mySheet.SetPagingPosition(1);
```

---

## 성능 최적화 팁

- `FitColWidth:0` 속성으로 불필요한 컬럼 자동 너비 계산 제외
- `DeferredVScroll:1`로 스크롤 시 렌더링 지연
- `RenderSheet(0/1)`로 대량 조작 시 렌더링 일시 중지/재개
- `WaitImageVisible = 0`으로 로딩 이미지 숨김

---

## 자주 발생하는 문제

### 조회 모드 선택
- **일반/중소 데이터**: `smLazyLoad` 사용 (기본, 권장)
- **대량 데이터 (10만건+)**: `smServerPaging2` + `DoSearchPaging()` 사용

### 저장 시 KeyField 검증
`KeyField:1`로 설정된 컬럼은 비어있으면 저장 시 경고가 발생합니다.

### Status 컬럼의 상태값
- `R`: 조회 (원본)
- `I`: 신규 입력
- `U`: 수정
- `D`: 삭제

### 이벤트 함수명 규칙
시트 ID + `_` + 이벤트명: `mySheet_OnSearchEnd`, `sheet2_OnClick` 등

### 날짜 Format
- `Ymd`: YYYY/MM/DD
- `Md`: MM/DD
- `Hm`: HH:MM
- `yyyy-MM-dd`: 2024-01-15

### 머지와 멀티라인 병용
멀티라인 레코드 사용 시 `MergeSheet: msFixedMerge + msHeaderOnly` 설정 필수

### 서버 페이징 조회 시 주의
`SearchMode:smServerPaging2`일 때는 반드시 `DoSearchPaging()` 함수를 사용해야 합니다.

### 엑셀 다운 시 숨겨진 컬럼 스킵
```javascript
function makeHiddenSkipCol(sobj) {
  var lc = sobj.LastCol();
  var colsArr = [];
  for (var i = 0; i <= lc; i++) {
    var coltype = sobj.GetCellProperty(0, i, "Type");
    if (sobj.GetColHidden(i) == 0 && coltype != "Seq" && coltype != "Status" && coltype != "DelCheck") {
      colsArr.push(i);
    }
  }
  return colsArr.join("|");
}
```

### 다중 시트 저장 패턴
```javascript
var param1 = mySheet.GetSaveString();
var param2 = mySheet2.GetSaveString();
var rtnData = mySheet.GetSaveData("save.jsp", param1 + "&" + param2);
mySheet.LoadSaveData(rtnData);
mySheet2.LoadSaveData(rtnData);
```

### 합계행 커스터마이징
```javascript
function mySheet_OnSearchEnd(code, msg) {
  mySheet.SetSumValue(0, "합 계/평 균");
  mySheet.SetCellAlign(mySheet.LastRow(), 0, "Center");
  mySheet.SetMergeCell(mySheet.LastRow(), 0, 1, 2);
}
```

### 소계행 포맷 설정
```javascript
mySheet.Rows.SumRow["C2Format"] = "#,##0 건";
mySheet.Rows.SumRow["C7Format"] = "평균 : #,##0";

// 소계행별 개별 설정
for (var key in mySheet.Rows) {
  if (mySheet.Rows[key]["SubSumRow"]) {
    mySheet.Rows[key]["C2Format"] = "#,##0 건";
  }
}
```

### AutoAvg 타입 & 합계행 설정
```javascript
{Header:"추천수", Type:"AutoAvg", Format:"#,###", SaveName:"sRcmn", FitColWidth:0}
{Header:"상품가격", Type:"AutoSum", Format:"#,###", SaveName:"sPrice",
  GroupSumType:"Sum", FitColWidth:0}

// 합계행 라벨 설정
mySheet.SetCellAlign(mySheet.LastRow(), "sPhone", "Right");
mySheet.SetSumValue(0, "sPhone", "추천수 평균:");
mySheet.SetCellAlign(mySheet.LastRow(), "sProdName", "Right");
mySheet.SetSumValue(0, "sProdName", "상품가격 합계:");
```

### 다중 시트 생성
```html
<script>
  createIBSheet("mySheet", "100%", "calc(50% - 3px)");
</script>
<div style="height:6px"></div>
<script>
  createIBSheet("mySheet2", "100%", "calc(50% - 3px)");
</script>
```

### Tab 이동 순서 설정
```javascript
mySheet.prevElement = "HoBong";
mySheet.nextElement = "mySheet2";
mySheet2.prevElement = "mySheet";
mySheet2.nextElement = "";
```
