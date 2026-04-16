# InitHeaders Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > InitHeaders Method

---

- **기능**

> 헤더에 들어갈 타이틀과 헤더기능을 지정한다.

- **Syntax**

|        |                                          |
|:------:|------------------------------------------|
| Syntax | ObjId.**InitHeaders(Headers, [Info])** |

- **Info**

> **Return**: None

| Parameter | Type     | 필수여부 | 설 명           |
| --------- | -------- | ---- | ------------- |
| Headers   | Object[] | 필수   | 헤더의 행별 정보를 설정 |
| Info      | Object   | 선택   | 헤더의 공통 정보를 설정 |

> **세부설정**

| 설정변수    |             | 타입      | 설명                                                                                                                                                                                                                                                                                                    |
| ------- | ----------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Headers | Text        | String  | 헤더에 표시할 Text를 "\|"로 연결한 문자열                                                                                                                                                                                                                                                                           |
| Headers | Align       | String  | 헤더 텍스트의 정렬방법 Default="Center"                                                                                                                                                                                                                                                                         |
| Headers | RowMerge    | Boolean | 헤더행의 가로머지 허용 여부 Default=1                                                                                                                                                                                                                                                                             |
| Info    | Sort        | Number  | 헤더 클릭을 통한 컬럼 Sort 허용 여부 \| 설정값 \| 설명                              \| \| --- \| ------------------------------- \| \| 0   \| 사용 안함                           \| \| 1   \| Sort 기능 사용 (Default)            \| \| 2   \| Sort 아이콘만 표시                    \| \| 3   \| colSpan 설정이 아닌 헤더 셀만 Sort 기능 사용 \| |
| Info    | ColMove     | Boolean | 헤더 컬럼 이동 가능 여부 Default=1                                                                                                                                                                                                                                                                              |
| Info    | ColResize   | Boolean | 컬럼 너비 조정 허용 여부 Default=1                                                                                                                                                                                                                                                                              |
| Info    | HeaderCheck | Boolean | 헤더에 전체 체크 표시 여부 Default=1                                                                                                                                                                                                                                                                             |

- **Example**

```javascript
//2줄 헤더타이틀을 설정한다.
var headers = [
{Text:"상태|삭제|직원정보|직원정보|직원정보", Align:" Center"} ,
{Text:"상태|삭제|직원명 |직원번호|입사일", Align:" Center"}
];
var info = {Sort:1, ColMove:1, ColResize:0, HeaderCheck:0};
mySheet.InitHeaders(headers,info);
```

- **제공 버전**

|  **7.0.0.0**  |                                                 |
|:-------------:|-------------------------------------------------|
|  **7.0.4.3**  | 헤더행 별 RowMerge 속성 추가                    |
|  **7.0.4.6**  | Sort 속성 개선 (아이콘만 표시하는 기능 추가)    |
| **7.0.13.24** | Sort 속성 개선 (colSpan 에 대한 예외 기능 추가) |