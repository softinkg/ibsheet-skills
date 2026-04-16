# 시트 생성 및 초기화

## 시트 객체 생성

### createIBSheet(id, width, height)
시트 HTML 객체를 생성합니다.
```javascript
createIBSheet("mySheet", "100%", "100%");
```

### createIBSheet2(element, id, width, height)
특정 DIV 내에 시트를 생성합니다.
```javascript
createIBSheet2(document.getElementById("sheetDiv"), "mySheet", "100%", "100%");
```

---

## 초기화

### IBS_InitSheet(sheetObj, initData)
시트를 초기화합니다. `initData` 객체는 `Cfg`, `HeaderMode`, `Cols`를 포함합니다.

### 대체 초기화 방식 (개별 메서드)
```javascript
mySheet.SetConfig(cfg);
mySheet.InitHeaders(headers, info);
mySheet.InitColumns(cols);
```

---

## Cfg (시트 전체 설정)

| 속성 | 설명 | 값 |
|------|------|-----|
| `SearchMode` | 조회 모드 | `smLazyLoad` (기본, 권장), `smServerPaging2` |
| `Page` | 한 페이지당 행 수 | 숫자 (예: 50) |
| `FrozenCol` | 고정 컬럼 수 | 숫자 (예: 3) |
| `MergeSheet` | 머지 모드 | `msNone`, `msHeaderOnly`, `msFixedMerge`, `msPrevColumnMerge` |
| `ToolTip` | 셀 툴팁 사용 | 0(미사용), 1(사용) |
| `MaxSort` | 최대 정렬 컬럼 수 | 숫자 (예: 3) |
| `AutoFitColWidth` | 자동 컬럼 너비 | `""`, `"init"`, `"init\|search\|resize"` |
| `CountPosition` | 건수 표시 위치 | 0~4 |
| `CountFormat` | 건수 표시 형식 | `"[SELECTDATAROW/TOTALROWS2]"` |
| `Undo` | Undo/Redo 사용 | 0(미사용), 1(사용) |
| `DeferredVScroll` | 스크롤 지연 렌더링 | 0, 1 |
| `ChildPage` | 트리 자식 페이지 수 | 숫자 (예: 5) |
| `UseGroupActionMenu` | 그룹 우클릭 메뉴 | 0, 1 |
| `MouseHoverMode` | 마우스 호버 | 0, 1, 2 |
| `PagingPosition` | 페이징 버튼 위치 | 0, 1 |
| `SumPosition` | 합계행 위치 | 0(상단), 1(하단) |
| `HeaderCheckMode` | 헤더 체크모드 | 0, 1 |
| `SelectionSummary` | 선택 범위 요약 | `"NotEmptyCell\|DelRow"` |
| `PrevColumnMergeMode` | 앞컬럼기준 머지 | 0, 1 |
| `DragMode` | 드래그 모드 | 0, 1 |
| `DragCell` | 셀 단위 드래그 | 0, 1 |

---

## HeaderMode (헤더 설정)

| 속성 | 설명 | 값 |
|------|------|-----|
| `Sort` | 정렬 사용 | 0, 1 |
| `ColMove` | 컬럼 이동 | 0, 1 |
| `ColResize` | 컬럼 크기 조절 | 0, 1 |
| `HeaderCheck` | 헤더 체크박스 | 0, 1 |
| `AutoFitColWidth` | 자동 컬럼 너비 | `""` |

---

## Cols 배열 공통 속성

| 속성 | 설명 | 예시 |
|------|------|------|
| `Header` | 헤더 텍스트 (멀티헤더: `\|`로 구분) | `"근태기간\|시작일"` |
| `Type` | 컬럼 타입 | `"Text"`, `"Int"` 등 |
| `SaveName` | 서버 전송시 키 이름 | `"COLUMN_ID"` |
| `Width` / `MinWidth` | 컬럼 너비 | 숫자 |
| `Align` | 정렬 | `"Left"`, `"Center"`, `"Right"` |
| `Edit` | 편집 가능 여부 | 0, 1 |
| `KeyField` | 필수 입력 필드 | 0, 1 |
| `Hidden` | 숨김 여부 | 0, 1 |
| `DefaultValue` | 기본값 | 값 |
| `ColMerge` | 행 방향 머지 | 0(미사용), 1(사용) |
| `Format` | 데이터 포맷 | `"#,###"`, `"Ymd"` 등 |
| `FitColWidth` | 자동너비 대상 | 0(제외), 기본(포함) |
| `Wrap` | 줄바꿈 | 0, 1 |
| `MultiLineText` | 멀티라인 입력 | 0, 1 |
| `FontColor` | 글자 색상 | `"#FF0000"` |
| `FontUnderline` | 밑줄 | 0, 1 |
| `BackColor` | 배경 색상 | `"#FAFAFA"` |
| `Cursor` | 커서 모양 | `"Pointer"`, `"Default"` |
| `Ellipsis` | 말줄임 표시 | 0, 1 |
| `Tip` | 툴팁 표시 | 0, 1 |
| `UpdateEdit` | 수정행 편집 | 0(불가), 1(가능, 기본) |
| `NumberSort` | 문자열 숫자정렬 | 0, 1 |
| `Validation` | 콤보 입력 검증 | 0, 1 |
| `PopupButton` | 팝업 버튼 표시 | 0, 1 |
| `PopupAlign` | 팝업 정렬 | `"Left"` |
| `RowSpan` | 멀티라인 행 병합 | 숫자 |
| `TreeCol` | 트리 컬럼 지정 | 0, 1 |
| `GroupWidth` | 그룹 시 너비 | 숫자 |
| `GroupSumType` | 그룹 합계 유형 | `"Sum"` |
| `TableCaption` | 모바일 캡션 | 0, 1 |
| `ShowMobile` | 모바일 표시 | 0, 1 |
| `AcceptKeys` | 허용 키 | `"N\|E"` (숫자\|영문) |
| `ExceptKeys` | 제외 키 | `"E"` |
| `FormatFix` | 포맷 고정 | 0, 1 |

---

## 예제: 전체 초기화 패턴

> 출처: `docs/examples/01/transaction.html`

```javascript
function LoadPage() {
  mySheet.RemoveAll();
  var initSheet = {};
  initSheet.Cfg = {
    SearchMode: smLazyLoad,
    ToolTip: 1,
    CountPosition: 2,
    CountFormat: "[SELECTDATAROW/TOTALROWS2]"
  };
  initSheet.HeaderMode = {Sort:1, ColMove:1, ColResize:1, HeaderCheck:1};
  initSheet.Cols = [
    {Header:"상태", Type:"Status", MinWidth:50, SaveName:"STATUS", Align:"Center"},
    {Header:"삭제", Type:"DelCheck", MinWidth:50, SaveName:"DEL_CHK"},
    {Header:"연도", Type:"Text", MinWidth:80, SaveName:"Release", Align:"Center"},
    {Header:"영화명", Type:"Text", SaveName:"MovieNm", MinWidth:150, KeyField:1, MultiLineText:1},
    {Header:"영화명(영문)", Type:"Text", MinWidth:150, SaveName:"EngNm", Wrap:1},
    {Header:"제작국가", Type:"Text", MinWidth:80, SaveName:"Country"},
    {Header:"유형", Type:"Text", MinWidth:60, SaveName:"CLS"},
    {Header:"장르", Type:"Text", MinWidth:120, SaveName:"Genres"},
    {Header:"제작상태", Type:"Text", MinWidth:80, SaveName:"STA", Align:"Center"},
    {Header:"감독", Type:"Text", MinWidth:100, SaveName:"Director"},
    {Header:"제작사", Type:"Text", MinWidth:100, SaveName:"Production"}
  ];
  IBS_InitSheet(mySheet, initSheet);

  mySheet.SetEditableColorDiff(1);
  mySheet.SetActionMenu("엑셀 파일 저장");

  doAction('search');
}
```

### 대체 초기화 방식 (개별 메서드) 예제

> 출처: `docs/examples/04/combo.html`

```javascript
mySheet.SetConfig({SearchMode:smLazyLoad, Page:50});
mySheet.InitHeaders(headers, {Sort:1, ColMove:1, ColResize:1});
mySheet.InitColumns(cols);
```
