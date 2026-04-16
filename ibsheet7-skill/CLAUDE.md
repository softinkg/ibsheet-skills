# IBSheet7 Skill

## 개요
IBSheet7은 (주)아이비리더스에서 개발한 한국 기업용 JavaScript 그리드 컴포넌트(V7.0.13.x)입니다.
이 프로젝트는 Claude Code가 IBSheet7 개발을 효과적으로 지원하기 위한 skill 파일을 관리합니다.

## Skill 구조
IBSheet7 개발 시 아래 파일을 참조하세요:

- **`SKILL.md`** - 메인 엔트리 포인트 (빠른 시작, CRUD 패턴, 기능별 인덱스)
- **`references/`** - 기능별 상세 레퍼런스 (API 설명 + 실전 예제 통합)
  - `01-initialization.md` - 시트 생성 및 초기화 (createIBSheet, Cfg, Cols)
  - `02-column-types.md` - 21개 컬럼 타입 (Status~Tree)
  - `03-data-operations.md` - 데이터 조회/저장 (DoSearch, DoSave, 서버 페이징)
  - `04-row-cell-column.md` - 행/셀/컬럼 조작 (DataInsert, GetCellValue, Frozen)
  - `05-events.md` - 이벤트 핸들러 (OnSearchEnd, OnClick, OnChange 등)
  - `06-formatting-constants.md` - 포맷 및 상수 (SearchMode, MergeSheet, Format)
  - `07-tree.md` - 트리 구조 (TreeCol, ShowTreeLevel, 동적 트리)
  - `08-filter-group-pivot.md` - 필터/그룹/소계/피벗
  - `09-merge-multiline.md` - 셀 병합/멀티라인 (MergeSheet, RowSpan)
  - `10-excel-pdf-print.md` - 엑셀/PDF/인쇄 (Down2Excel, LoadExcel)
  - `11-advanced.md` - 고급 기능 (CalcLogic, Drag&Drop, Undo, 간트차트)
  - `12-helpers-tips.md` - 헬퍼 함수 및 팁 (폼 연동, 성능, 자주 발생하는 문제)

## 참고자료
- ibsheet7 개발자 가이드 문서 위치 => ./docs/IBSheetHTML개발자가이드_V7.0.13.x.doc
- 예제 파일들 위치 => ./docs/examples/*
- 공식 개발자 가이드 매뉴얼(MD) 위치 => ./references/ibsheet7-official-manual/
  - 전체 목차: `index.md`
  - Config(159개): `07-ibsheet-config/`
  - Events(68개): `08-ibsheet-events/`
  - Methods(320개+): `09-ibsheet-methods/`
  - 부록(컬럼 속성, 자주 쓰는 메서드 등): `11-appendix/`

## 개발 가이드
- IBSheet7 코드 작성 시 `SKILL.md`를 엔트리 포인트로, 해당 기능의 `references/` 파일을 상세 참조
- 이벤트 함수명은 반드시 `시트ID_이벤트명` 규칙을 따름 (예: `mySheet_OnSearchEnd`)
- 조회 모드: 일반 데이터는 `smLazyLoad`, 대량 데이터는 `smServerPaging2` 사용
