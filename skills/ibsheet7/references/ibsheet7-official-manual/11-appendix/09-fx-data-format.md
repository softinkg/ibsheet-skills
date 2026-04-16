# 2. Fx(Formatted) 조회 모드의 허용 데이터 포맷

> **IBSheet7 개발자 가이드** > Appendix > 2. Fx(Formatted) 조회 모드의 허용 데이터 포맷

---

> Dosearch 또는 LoadSearchData 메소드의 Fx 옵션 사용시 타입별 허용하는 포맷 값은 아래의 표와 같다.

| 컬럼타입       | 포맷     | 허용값           | 사용가능예               | 사용불가능예            | 비고                         |
| ---------- | ------ | ------------- | ------------------- | ----------------- | -------------------------- |
| Text       | 일반     | 문자열           |                     |                   |                            |
| Text       | 사용자 포맷 | 포맷을제외한 문자열    | 7912121022345       | 791212-1022345    |                            |
| Text       | 날짜     | Date 타입 참고    |                     |                   |                            |
| Popup      | 일반     | 문자열           |                     |                   |                            |
| Popup      | 날짜     | Date 타입 참고    |                     |                   |                            |
| Pass       |        | 문자열           |                     |                   |                            |
| Date       | 날짜     | 날짜포맷 문자열      | 2012-02-16          | 20120216          | 년월일 구분자는 설정포맷과 틀려도됨        |
| Date       | 시간     | 날짜포맷 문자열      | 13:15:16            | 131516            |                            |
| Date       | 날짜+시간  | 날짜, 시간포맷 문자열  | 2012-02-16 13:15:16 | 20120216131516    | 날짜와 시간 사이는 스페이스로 구분        |
| Int        |        | 포맷을 제외한 숫자값   | 1234567             | 1,234,567         |                            |
| Float      |        | 포맷을 제외한 숫자값   | 123456.789          | 123,456.789       |                            |
| AutoSum    | Int    | 포맷을 제외한 숫자값   | 1234567             | 1,234,567         |                            |
|            | Float  | 포맷을 제외한 숫자값   | 123456.789          | 123,456.789       |                            |
| AutoAvg    | Int    | 포맷을 제외한 숫자값   | 1234567             | 1,234,567         |                            |
|            | Float  | 포맷을 제외한 숫자값   | 123456.789          | 123,456.789       |                            |
| CheckBox   |        | 0 또는 1        |                     | 0, 1을 제외한 문자열     |                            |
| DelCheck   |        | 0 또는 1        |                     | 0, 1을 제외한 문자열     |                            |
| DummyCheck |        | 0 또는 1        |                     | 0, 1을 제외한 문자열     |                            |
| Radio      |        | 0 또는 1        |                     | 0, 1을 제외한 문자열     |                            |
| Combo      |        | 설정 ComboCode값 |                     |                   | InitCombo NoMatchText 사용불가 |
| ComboEdit  |        | 설정 ComboCode값 |                     |                   | InitCombo NoMatchText 사용불가 |
| Image      |        | Image Url     |                     |                   |                            |
| Seq        |        | 공백            |                     | 문자열               |                            |
| Status     |        | I, D          |                     | 공백, I, D를 제외한 문자열 |                            |

Fx:1 사용시 OnRowSearchEnd() 이벤트가 생략된다.

Fx:2 가 7.0.5.4 버젼 부터 추가되었다.

이 옵션을 사용하는 경우 아래와 같은 여러가지 기능의 제한이 생기는 대신 조회 속도를 크게 향상시킨다.

1.  조회 모드  
    smClientPaging, smLazyLoad 에서만 사용이 가능하다.

2.  데이터 포멧  
    XML 형식의 데이터는 지원하지 않으며 JSON형태만 지원한다. 그리고 JSON 형식에서 UseJsonAttribute를 통해 행단위,셀단위 서식은 지원하지 않는다.  
    조회데이터 배열 명인 "Data" 도 대/소문자를 반드시 지켜야 인식한다.

3.  머지 유형  
    데이터 영역의 머지는 허용되지 않으며 msNone나msHeaderOnly 형식의 머지만 사용할 수 있다.

4.  계산 기능  
    ShowSubSum()함수를 통한 소계/누계 기능은 지원하지 않고, InitColumns()함수의 Calculogin(열간 계산식) 기능도 지원하지 않는다.

5.  시트 구조  
    트리형식이나 다중라인 레코드 구조의 시트는 지원하지 않는다.

6.  LoadSearchData의 Option 파라미터  
    Wait와 Sync를 제외한 다른 기능은 지원하지 않는다.

7.  이벤트  
    조회 후 발생하는 OnSearchEnd 이벤트만 지원하며, OnLoadData, OnRownSearchEnd, OnDecryption 과 같은 이벤트는 발생하지 않는다.

8.  그 외 옵션  
    DataAutoTrim,FrozenRows,DefaultValue 설정이 지원되지 않는다.

그외 각 컬럼의 Type 별 조회 허용 유형  
아래 타입/포멧의 경우 조회 과정에서 서버로부터 넘어온 데이터를 무시하고 시트에 표시하지 않을 뿐 조회 된 이후에는 동일하게 동작한다.

| 컬럼 타입                     | 세부 내용                                                         | 불허 형식                        |
| ------------------------- | ------------------------------------------------------------- | ---------------------------- |
| Text,Popup                |                                                               | Date 포멧사용 불가                 |
| CheckBox,DummyCheck       | 0/1 값만 사용가능                                                   | TrueValue/FalseValue값 무시     |
| Radio,DelCheck            |                                                               | 조회 데이터 표시 안함                 |
| Combo                     | ComboCode값 맵핑                                                 | InitComboNoMatchText() 설정 무시 |
| ComboEdit                 | ComboText값 맵핑                                                 | InitComboNoMatchText() 설정 무시 |
| Int,Float,AutoSum,AutoAvg | 콤마가 제거된 숫자형식만 사용가능                                            |                              |
| Date                      | Ymd,Ym,Md만 사용 가능하며, 조회시 구분자를 포함하여 데이터를 조회해야 함. ex) 1987-12-26 | Hms,Hm,YmdHms 형식 사용 불가       |
| Status,Result             |                                                               | 조회 데이터 표시 안함                 |