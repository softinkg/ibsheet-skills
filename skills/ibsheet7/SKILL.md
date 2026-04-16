---
name: ibsheet7
description: IBSheet7 한국 기업용 JavaScript 그리드 컴포넌트(V7.0.13.x) 개발 지원 skill. 시트 생성, 초기화, CRUD, 이벤트, 엑셀/PDF 등 전체 API 레퍼런스 제공.
---

# IBSheet7 Skill

IBSheet7은 (주)아이비리더스에서 개발한 한국 기업용 JavaScript 그리드 컴포넌트(V7.0.13.x)입니다.

---

## 빠른 시작

### 필수 스크립트 로드
```html
<script language="javascript" src="ibsheetinfo.js"></script>
<script language="javascript" src="ibsheet.js"></script>
<!-- 엑셀 기능 사용 시 -->
<script language="javascript" src="ibexcel.js"></script>
```

### 시트 생성 → 초기화 → 조회 패턴
```javascript
// 1. 시트 객체 생성
createIBSheet("mySheet", "100%", "100%");

function LoadPage() {
  // 2. 초기화 객체 구성
  var initSheet = {};
  initSheet.Cfg = {SearchMode: smLazyLoad, Page: 50};
  initSheet.HeaderMode = {Sort:1, ColMove:1, ColResize:1, HeaderCheck:1};
  initSheet.Cols = [
    {Header:"상태", Type:"Status", SaveName:"STATUS", Align:"Center"},
    {Header:"삭제", Type:"DelCheck", SaveName:"DEL_CHK"},
    {Header:"이름", Type:"Text", SaveName:"NAME", KeyField:1, MinWidth:100},
    {Header:"금액", Type:"Int", SaveName:"AMT", Format:"#,###", Align:"Right"}
  ];

  // 3. 시트에 설정 적용
  IBS_InitSheet(mySheet, initSheet);

  // 4. 데이터 조회
  mySheet.DoSearch("data.json");
}
```

### 기본 CRUD 패턴
```javascript
// 조회
mySheet.DoSearch("searchUrl.json");

// 조회 (데이터를 직접 로드)
var json = mySheet.GetSearchData("searchUrl.json");
mySheet.LoadSearchData(json);

// 행 추가
var row = mySheet.DataInsert();

// 저장 (서버로 전송)
mySheet.DoSave("saveUrl.jsp");

// 저장 문자열/JSON 추출
var saveStr = mySheet.GetSaveString();
var saveJson = mySheet.GetSaveJson();

// 전체 데이터 저장
mySheet.DoAllSave("saveUrl.jsp");

// 데이터 초기화
mySheet.RemoveAll();

// ibsheet7 객체 초기화(ibsheet7 객체 생성 후 다시 생성하는 경우)
mySheet = mySheet.Reset();
// 이후에 IBS_InitSheet(...) 를 통해 시트를 다시 설정
```

---

## 기능별 레퍼런스

| 파일 | 설명 | 주요 API |
|------|------|----------|
| [01-initialization.md](references/01-initialization.md) | 시트 생성 및 초기화 | `createIBSheet`, `IBS_InitSheet`, Cfg, HeaderMode, Cols |
| [02-column-types.md](references/02-column-types.md) | 21개 컬럼 타입 | Status, Text, Int, Float, Date, Combo, CheckBox, AutoSum, Button, Popup, Tree 등 |
| [03-data-operations.md](references/03-data-operations.md) | 데이터 조회/저장 | `DoSearch`, `DoSave`, `GetSaveString`, `GetSaveJson`, `DoSearchPaging` |
| [04-row-cell-column.md](references/04-row-cell-column.md) | 행/셀/컬럼 조작 | `DataInsert`, `GetCellValue`, `SetCellValue`, `SetColHidden`, `SetFrozenCol` |
| [05-events.md](references/05-events.md) | 이벤트 핸들러 | `OnSearchEnd`, `OnClick`, `OnChange`, `OnButtonClick`, `OnPopupClick` |
| [06-formatting-constants.md](references/06-formatting-constants.md) | 포맷 및 상수 | SearchMode, MergeSheet, SumType, Format |
| [07-tree.md](references/07-tree.md) | 트리 구조 | `TreeCol`, `ShowTreeLevel`, `SetTreeActionMode`, `OnTreeChild` |
| [08-filter-group-pivot.md](references/08-filter-group-pivot.md) | 필터/그룹/소계/피벗 | `ShowFilterRow`, `ShowGroupRow`, `ShowSubSum`, `ShowPivotDialog` |
| [09-merge-multiline.md](references/09-merge-multiline.md) | 셀 병합/멀티라인 | `SetMergeSheet`, `SetMergeCell`, MergeSheet, RowSpan/ColSpan |
| [10-excel-pdf-print.md](references/10-excel-pdf-print.md) | 엑셀/PDF/인쇄 | `Down2Excel`, `LoadExcel`, `DirectDown2Excel`, `Down2Pdf`, `DoPrint` |
| [11-advanced.md](references/11-advanced.md) | 고급 기능 | CalcLogic, Drag&Drop, Undo/Redo, 간트차트, 찾기 |
| [12-helpers-tips.md](references/12-helpers-tips.md) | 헬퍼 함수 및 팁 | 폼 연동, 시트 설정, 성능 최적화, 자주 발생하는 문제 |

---

## 공식 개발자 가이드 매뉴얼

IBSheet7 공식 개발자 가이드(V7.0.13.x)가 MD 형식으로 제공됩니다.
경로: `references/ibsheet7-official-manual/`

| 폴더 | 설명 | 주요 내용 |
|------|------|-----------|
| [index.md](references/ibsheet7-official-manual/index.md) | 전체 목차 | 개발 절차, 데이터 구조, Config, Events, Methods, Global Module, Appendix |
| [04-development-procedure/](references/ibsheet7-official-manual/04-development-procedure/index.md) | 개발 절차 | JS 파일 링크, 객체 생성, 초기화, 조회/저장 XML·JSON 구현 |
| [06-data-structure/](references/ibsheet7-official-manual/06-data-structure/index.md) | 데이터 구조 | XML, JSON, Tree JSON, 엑셀 리포트 XML 형식 |
| [07-ibsheet-config/](references/ibsheet7-official-manual/07-ibsheet-config/index.md) | IBSheet Config | 159개 설정 항목 전체 (Alternate ~ WheelScrollSize) |
| [08-ibsheet-events/](references/ibsheet7-official-manual/08-ibsheet-events/index.md) | IBSheet Events | 68개 이벤트 전체 (OnAfterColumnMove ~ OnWaitTimeOut) |
| [09-ibsheet-methods/](references/ibsheet7-official-manual/09-ibsheet-methods/index.md) | IBSheet Methods | 320개+ 메서드 전체 (ActionMenu ~ WaitTimeOut) |
| [10-ibsheet-global-module/](references/ibsheet7-official-manual/10-ibsheet-global-module/index.md) | IBSheet Global Module | IBCalendar (SetTheme, Show, Close) |
| [11-appendix/](references/ibsheet7-official-manual/11-appendix/index.md) | 부록 | 컬럼 타입별 속성, Fx 조회 모드, 테마 만들기, 엑셀 머지, 자주 쓰는 메서드 |

> 특정 Config·Event·Method를 찾을 때는 해당 폴더의 `index.md`를 먼저 확인하세요.

---

## 핵심 규칙

- **이벤트 명명**: 반드시 `시트ID_이벤트명` 규칙 (예: `mySheet_OnSearchEnd`)
- **조회 모드**: 일반 데이터 → `smLazyLoad`, 대량 데이터(10만건+) → `smServerPaging2` + `DoSearchPaging()`
- **필수 입력**: `KeyField:1` 설정 시 빈 값이면 저장 경고 발생
- **Status 상태값**: R(조회/원본), I(신규 입력), U(수정), D(삭제)
- **멀티라인+머지**: `MergeSheet: msFixedMerge + msHeaderOnly` 필수
- **멀티헤더**: Header 문자열에 `|` 구분자 사용 (예: `"근태기간|시작일"`)
