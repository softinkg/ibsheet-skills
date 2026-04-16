# 6. 아이비시트에서 자주 사용되는 메서드 정리

> **IBSheet7 개발자 가이드** > Appendix > 6. 아이비시트에서 자주 사용되는 메서드 정리

---

1\. Data Read/Write

| Return값 유형 | Method 명      | 내용                                 |
|---------------|----------------|--------------------------------------|
| String        | CellValue      | 셀 데이터 Read/Write                 |
| String        | CellText       | 셀 데이터 Read/Write                 |
| JSON Object   | RowData        | 행 데이터 Read/Write                 |
| Query String  | RowSaveStr     | 행 데이터 Read                       |
|               | LoadSearchData | 조회 데이터 XML/JSON Write           |
|               | LoadSaveData   | 저장 데이터 XML/JSON Write           |
| String        | GetEditText    | 편집중인 셀의 데이터 Read            |
| String        | SumValue       | 합계행 안에 셀 데이터 Read/Write     |
| JSON Object   | GetSaveJson    | 시트 전체 데이터 Read                |
| Query String  | GetSaveString  | 시트 전체 데이터 Read                |
| Object        | GetSheetHtml   | 시트 전체 데이터를 HTML양식으로 Read |

2\. 최초 조회된 값 확인/변경

| Return값 유형 | Method 명       | 내용                           |
|---------------|-----------------|--------------------------------|
|               | ReturnData      | 행을 최초 조회했던 값으로 변경 |
|               | ReturnCellData  | 셀을 최초 조회했던 값으로 변경 |
| String        | CellSearchValue | 셀에 대한 조회 데이터 확인     |

3\. 행/열 인덱스

| Return값 유형 | Method 명  | 내용                                            |
|---------------|------------|-------------------------------------------------|
| Int           | LastRow    | 마지막 행의 Index                               |
| Int           | LastCol    | 마지막 열의 인덱스                              |
| Int           | HeaderRows | 첫번째 데이터 행의 인덱스                       |
| Int           | SearchRows | 조회한 데이터 행수 (상태가 R인 데이터 행 수)    |
| Int           | TopRow     | 현재 화면에 보여지는 행중 최 상단의 행 인덱스   |
| Int           | LeftCol    | 현재 화면에 보여지는 열중에 최 좌측의 열 인덱스 |
| Int           | SelectRow  | 현재 선택된(포커스 된) 행의 인덱스              |
| Int           | SelectCol  | 현재 선택된(포커스 된) 열의 인덱스              |
|               | SelectCell | 특정 셀로 포커스 이동                           |
| Int or String | FindSumRow | 합계행의 인덱스                                 |

4\. 찾기 기능

| Return값 유형 | Method 명        | 내용                                       |
|---------------|------------------|--------------------------------------------|
| Int           | FindText         | 열에서 특정 String문자 찾기                |
| String        | FindSubSumRow    | 여러개의 소계행 인덱스 찾기                |
| String        | FindCheckedRow   | 체크박스 컬럼에 체크된 행 찾기             |
| String        | FindStatusRow    | 특정 상태를 갖는 모든 행 찾기              |
| String        | GetSelectionRows | 마우스로 드레그 하여 선택한 영역 행 인덱스 |
| String        | GetSelectionCols | 마우스로 드레그 하여 선택한 영역 열 인덱스 |

5\. Tree 기능 관련 함수

| Return값 유형 | Method 명         | 내용                               |
|---------------|-------------------|------------------------------------|
| Int           | RowLevel          | 노드의 Level(depth) Read/Write     |
| Boolean       | IsHaveChild       | 자식노드 존재 여부 확인            |
| Int           | GetPrevSiblingRow | 자신과 같은 Level의 상위 행 인덱스 |
| Int           | GetNextSiblingRow | 자신과 같은 Level의 하위 행 인덱스 |
| Int           | GetParentRow      | 부모 행 인덱스                     |
| String        | GetChildRows      | 자식 행 전체 인덱스                |
| Int           | GetLastChildRow   | 마지막 자식 행 인덱스              |
| Int           | GetChildNodeCount | 자식행 개수                        |
|               | ShowTreeLevel     | 특정 Level까지 접거나 펼침         |

6\. File import/export

| Return값 유형 | Method 명 | 내용 |
|----|----|----|
|  | Down2Excel | 시트의 데이터를 엑셀파일로 export |
|  | Down2Text | 시트의 데이터를 text 파일로 export |
|  | Down2Pdf | 시트의 데이터를 PDF파일로 export |
|  | DirectDown2Excel | 시트의 헤더정보와 디비의 데이터 정보를 합쳐 엑셀파일로 export |
|  | LoadExcel | 엑셀 파일을 시트위로 import |
|  | LoadText | text 파일을 시트위로 import |
|  | DirectLoadExcel | 엑셀 파일을 디비로 바로 저장 |
|  | Down2ExcelBuffer | 두개 이상의 시트를 하나의 엑셀파일로 export |
|  | SetDown2ExcelConfig | 엑셀 export시 공통 설정 |
|  | OnDownFinish | 다운로드 완료 후 이벤트 |
|  | OnBeforeDownload | 서버로 데이터 전달 직전 이벤트 |
|  | OnLoadExcel | 엑셀 파일 업로드 이후 이벤트 |

7\. 건수정보 표시 줄 관련

| Return값 유형 | Method 명 | 내용 |
|----|----|----|
|  | CountPosition | 건수표시 위치 설정 |
|  | CountFormat | 건수표시 포멧 설정 |
|  | CountInfoElement | 건수표시를 외부 객체에 설정/확인 |
|  | SelectionSummaryInfoElement | Summary정보를 외부 객체에 설정/확인 |
|  | SelectionSummary(in SetConfig) | 드레그 영역에 대한 Summary정보 표시 |
|  | PagingPosition | 페이지 네비게이션 버튼 표시 |

8\. Tab,Enter 입력시 동작 결정

| Return값 유형 | Method 명 | 내용 |
|----|----|----|
|  | TabBehavior | 포커스 상태에서 Tab키 다운시 동작방식 결정 |
|  | EnterBehavior | 포커스 상태에서 Enter키 다운시 동작방식 결정 |
|  | EditTabBehavior | 편집 중 Tab키 다운시 동작방식 결정 |
|  | EditEnterBehavior | 편집 중 Enter키 다운시 동작방식 결정 |
|  | OnTab | Tab키를 통해 이동시 발생하는 이벤트 |

9\. 기타 자주 사용되는 메서드

RemoveAll 조회 데이터 전체 삭제

Reset 시트 객체 초기화

RowHidden 행 보이기/감추기

ColHidden 열 보이기/감추기

IsDataModified 시트의 수정 여부 확인

ColSaveName 열의 인덱스를 기준으로 SaveName을 확인

SaveNameCol 열의 SaveName을 기준으로 인덱스를 확인