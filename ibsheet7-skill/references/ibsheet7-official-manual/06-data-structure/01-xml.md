# 6.1 XML

> **IBSheet7 개발자 가이드** > 데이터 구조 > 6.1 XML

---

### 6.1.1 조회 XML

> 조회 함수를 통해 읽어들이는 XML 전체 구조는 다음과 같다.

```
<?xml version='1.0' ?>
<SHEET>
<!-- 선택항목. ETC-DATA 요소 -->

<ETC-DATA>

<ETC KEY="key_name">key_value</ETC>

</ETC-DATA>
<!-- 선택항목. Message 요소 -->

<MESSAGE>메시지</MESSAGE>
<!-- 필수항목. DATA 요소 -->
<DATA TOTAL="50"
COLORDER="prod_nm|pay|enter_date|book_chk"
COLSEPARATOR="구분자">
<!-- 필수항목. TR 요소 : 행단위 설정 -->
<TR LEVEL="" HAVECHILD="">
<!-- 필수항목. TD 요소 : 데이터단위 설정 -->
<TD> 조회된 데이터 </TD>
</TR>
</DATA>
<!-- 필수항목. Result 요소 -->
<RESULT CODE="" MESSAGE=""></RESULT>
</SHEET>
```

> 위의 조회 XML에서 사용하는 XML요소는 다음과 같이 필수 항목과 선택 항목으로 나누어 진다.

|          |          |                                    |
|:--------:|:--------:|:----------------------------------:|
|  요소명  | 필수여부 |               설 명                |
|  SHEET   |   필수   |     조회 데이터의 최상위 요소      |
|   DATA   |   필수   |      조회 데이터의 시작 요소       |
|    TR    |   필수   | 조회 데이터의 각 행 단위 설정 요소 |
|    TD    |   필수   |  조회 데이터의 셀 단위 설정 요소   |
| ETC-DATA |   선택   |       기타 데이터 설정 요소        |
| MESSAGE  |   선택   |       서버 메시지 설정 요소        |
|  RESULT  |   선택   |      서버 처리 결과 설정 요소      |### 6.1.1.1 SHEET 요소

> 조회된 데이터의 최상위를 의미 한다.
>
> 이 요소는 조회 XML의 최 상위 요소로 XML 기본 정의 아래 반드시 하나만 사용해야 한다. 이 요소 안에 사용되는 <DATA> 요소는 조회된 데이터를 의미하며 단 하나만 사용해야 한다. <ETC-DATA> 요소는 조회된 데이터 이외의 기타 데이터를 가져오는 요소로 여러 개 사용할 수 있다.

- **속성**

| 속성  | 설 명 |
| --- | --- |
| 없음  |     |

- **Example**

```
<!-- 조회된 내역이 없는 경우 -->
<?xml version="1.0" ?>
<SHEET>
<DATA>
</DATA>
</SHEET>
<!—일반 조회의 경우 -->
<?xml version="1.0" ?>
<SHEET>
<DATA>
<TR>
<TD>R</TD>
<TD>1234</TD>
<TD>가나다라</TD>
</TR>
</DATA>
</SHEET>
```

- **제공 버전**

> **7.0.0.0**### 6.1.1.2 DATA 요소

> 조회된 데이터 영역을 의미하는 요소로 일반적으로 <SHEET> 요소 안에 사용하여 이 요소 안의 데이터를 조회된 데이터로 표현한다.
>
> 이 요소 안에 사용되는 <TR> 요소는 조회된 각 행의 데이터를 의미하며, 하나도 사용되지 않은 경우 조회된 데이터가 없는 것으로 처리된다.
>
> TOTAL 속성은 서버 페이징 조회 (실시간 조회)를 하는 경우에만 사용하며 전체 데이터 건수를 설정 한다. 이 속성 값에 따라 스크롤 사이즈가 설정된다.
>
> COLORDER 속성은 <TR>요소 하단의 <TD>요소 순서가 컬럼의 순서와 다를 때 사용 한다. 이 속성을 사용할 경우 반드시 각 데이터 별로 SaveName을 설정해야 하며 조회한 데이터의 컬럼 순서를 SaveName 과 "\|"를 연결한 문자열로 이 속성에 설정한다. 예를 들어 실제 컬럼 순서는 prod_nm -> count -> amt 라고 할때 ColOrder가 설정되지 않은 경우 <TD>는 반드시 prod_nm -> count -> amt 순서로 조회해야 한다. 조회 시 Data 요소를 <DATA COLORDER="amt \| prod_nm \| count">라고 설정하면 <TD>는 amt -> prod_nm -> count 순서로 조회해야 한다.
>
> COLSEPARATOR 속성은 <TR> 요소 하단에 <TD>요소를 사용하지 않고 특정 구분자로 구분하여 조회할 때 설정 한다.

- **속성**

| 속성           | 설 명                                         |
| ------------ | ------------------------------------------- |
| TOTAL        | 조회 할 전체 건수 실시간 서버 페이징 조회시 이 속성을 반드시 설정해야 함. |
| COLORDER     | 컬럼 순서를 SaveName 과 "\|"를 연결한 문자열             |
| COLSEPARATOR | 컬럼을 구분하는 문자열                                |

- **Example**

```
<!-- 전체건수가 1000건이고, 조회건수가 100건인경우 -->
<?xml version="1.0" ?>
<SHEET>
<DATA TOTAL="1000">
<TR>(조회된 데이터 중략)</TR>
</DATA>
</SHEET>
<!-- COLORDER 사용 조회 -->
<?xml version="1.0" ?>
<SHEET>
<DATA COLORDER=" amt | prod_nm | count ">
<TR>(조회된 데이터 중략)</TR>
</DATA>
</SHEET>
<!-- COLSEPARATOR 사용 조회 -->
<?xml version="1.0" ?>
<SHEET>
<DATA COLSEPARATOR="|">
<TR> |001|10000|아이비리더스|1</TR>
<TR> |001|10000|아이비리더스|1</TR>
</DATA>
</SHEET>
```

- **제공 버전**

> **7.0.0.0**### 6.1.1.3 TR 요소

> 조회된 데이터의 각 행 단위 데이터를 의미 한다.
>
> 이 요소는 <DATA>요소 하위에 사용되며 조회된 행의 개수만큼 반복 사용한다.
>
> <DATA>요소 안에 이 요소가 없는 경우 조회된 데이터가 없는 것으로 처리 된다.
>
> LEVEL 속성은 트리 구조 조회시 해당 행의 트리 레벨 정보를 설정한다.
>
> 최상위 레벨은 0으로 설정한다.

- **속성**

|  |  |  |
|:--:|:--:|:--:|
| **속성** | **Type** | **설 명** |
| **BackColor** | String | 해당 행의 배경색상 |
| **Drag** | Boolean | 해당 행의 Drag 허용 여부 (Default = 1) |
| **Edit** | Boolean | 해당 행의 Edit 허용 여부 |
| **Expand** | Boolean | 해당 행의 자식 레벨 데이터를 펼칠것인지 여부 |
| **FontColor** | String | 해당 행의 폰트색상 |
| **HaveChild** | Boolean | 트리형태일때 해당행의 Child 데이터가 있으면서 조회하지 않는경우 사용, 나중에 [OnTreeChild Event](mk:@MSITStore:C:\Users\dort\Desktop\IBSheet.chm::/event/OnTreeChild.html)가 발생할 수 있는 행 설정 |
| **Hidden** | Boolean | 해당 행의 숨김 여부 |
| **Level** | Number | 해당 행의 트리 레벨 |
| **Merge** | Boolean | 해당 행의 RowMerge 허용 여부 |
| **Sum** | Boolean | 해당 행의 합계 계산 포함 여부 |
| **TreeCheck** | Boolean | 트리 컬럼의 체크박스 값 |

- **Example**

```
<!-- 트리 형태의 데이터 조회하기 1-->
<?xml version="1.0" ?>
<SHEET>
<DATA>
<TR LEVEL="0">(조회된 데이터 중략)</TR>
<TR LEVEL="1">(조회된 데이터 중략)</TR>
<TR LEVEL="2">(조회된 데이터 중략)</TR>
<TR LEVEL="2">(조회된 데이터 중략)</TR>
<TR LEVEL="1">(조회된 데이터 중략)</TR>
<TR LEVEL="2">(조회된 데이터 중략)</TR>
<TR LEVEL="2">(조회된 데이터 중략)</TR>
<TR LEVEL="2">(조회된 데이터 중략)</TR>
</DATA>
</SHEET>
<!-- 트리 형태의 데이터 조회하기 2. Child 데이터 조회하지 않고 나중에 조회하기-->
<?xml version="1.0" ?>
<SHEET>
<DATA>
<TR LEVEL="0">(조회된 데이터 중략)</TR>
<TR LEVEL="1" HAVECHILD="1">(조회된 데이터 중략)</TR>
<TR LEVEL="1" HAVECHILD="1">(조회된 데이터 중략)</TR>
</DATA>
</SHEET>
```

- **제공 버전**

> **7.0.0.0**
>
> **  **### 6.1.1.4 TD 요소

> 해당 행의 각 컬럼별 조회 데이터를 의미 한다.
>
> 이 요소는 <TR>요소 안에 사용되며 해당 행의 컬럼개수 만큼 반복 사용한다.

- **속성**

|                   |                                                   |
|:-----------------:|:-------------------------------------------------:|
|     **속성**      |                     **설 명**                     |
|     **Align**     |                     정렬 설정                     |
|   **BackColor**   |                해당 셀의 배경색상                 |
|   **ComboCode**   |    콤보타입일경우 해당셀의 콤보 코드값을 설정     |
|   **ComboText**   |   콤보타입일경우 해당셀의 콤보 텍스트값을 설정    |
|     **Edit**      |             해당 셀의 Edit 허용 여부              |
|   **FontBold**    |                  Bold 설정 여부                   |
|   **FontColor**   |                해당 셀의 폰트색상                 |
|  **FontItalic**   |                기울이기 설정 여부                 |
|  **FontStrike**   |                 취소선 설정 여부                  |
| **FontUnderline** |                  밑줄 설정 여부                   |
|     **Image**     | 해당 셀의 이미지 경로 (ImageList 인덱스 사용가능) |
|   **SortValue**   |        셀의 원래 값 대신 소팅시 사용할 값         |
|    **ToolTip**    |             표시할 풍선도움말 문자열              |

- **Example**

```
<!--조회된 내역-->
<?xml version="1.0" ?>
<SHEET>
<DATA>
<TR BackColor="#FFFF00" FontColor="#00FF00" EDIT="0">
<TD BackColor="#FF0000" Edit="0"></TD>
<TD FontColor="#00FF00" Edit="0"></TD>
<TD Image="0">006</TD>
<TD SortValue="001">>홍길동</TD>
<TD>10000</TD>
<TD></TD>
<TD>20030201</TD>
<TD>200302</TD>
<TD>0201</TD>
<TD>770101-1234567</TD>
<TD>123-45-67890</TD>
<TD>1111-2222-3333-4444</TD>
<TD>가</TD>
<TD>abc</TD>
<TD>150-080</TD>
<TD>0</TD>
<TD>180101</TD>
<TD ComboText="대기|진행|완료" ComboCode="1|2|3">0101</TD>
<TD></TD>
</TR>
</DATA>
</SHEET>
```

- **제공 버전**

|  **7.0.0.0**   |                |
|:--------------:|----------------|
| **7.0.13.271** | SortValue 추가 |

> **  **### 6.1.1.5 ETC-DATA 요소

> 조회 데이터 이외의 여분의 기타 데이터를 의미 한다.
>
> 이 요소는 IB Sheet 내의 데이터 이외의 데이터를 가져와 다른 용도로 사용하는 경우에 설정하여 사용한다. 이 요소를 통해 가져온 데이터는 EtcData Method를 통해 확인 할 수 있고 다른 값으로도 변경이 가능 하다.

- **속성**

|      |              |
|:----:|:------------:|
| 속성 |    설 명     |
| KEY  | 대표 키 이름 |

- **Example**

```
<!--조회 시 사용하기-->
<?xml version="1.0" ?>
<SHEET>
<ETC-DATA>
<ETC KEY="name">홍길동</ETC>
<ETC KEY="age">30</ETC>
</ETC-DATA>
<DATA>
(조회된 데이터 중략)
</DATA>
</SHEET>
<!--저장 시 사용하기-->
<?xml version="1.0" ?>
<SHEET>
<ETC-DATA>
<ETC KEY="name">홍길동</ETC>
<ETC KEY="age">30</ETC>
</ETC-DATA>
<RESULT CODE="0" Message="결과 메시지"/>
</SHEET>
```

- **제공 버전**

> **7.0.0.0**### 6.1.1.6 MESSAGE 요소

> 서버로부터 조회 처리 중 발생하는 메시지를 처리하기 위한 요소 이다.
>
> 이 요소가 설정된 경우 조회 완료 후 발생하는 OnSearchEnd 이벤트에서 message 인자에 값이 설정되어 이벤트가 발생한다.

- **속성**

| 속성  | 설 명 |
| --- | --- |
| 없음  |     |

- **Example**

```
<!--조회 시 사용하기-->
<?xml version="1.0" ?>
<SHEET>
<MESSAGE>조회가 완료되었습니다.</MESSAGE>
<DATA>
(조회된 데이터 중략)
</DATA>
</SHEET>
```

- **제공 버전**

> **7.0.0.0**
>
> **  **### 6.1.1.7 RESULT 요소

> 조회 데이터의 결과를 의미 한다.
>
> CODE 속성은 조회 처리 결과에 대한 코드이며 정수값을 설정 한다.
>
> 설정 값이 0 이상인 경우 정상 처리로 0보다 작은 경우는 실패 처리한다..
>
> MESSAGE 속성은 처리 결과에 대한 메시지를 설정한다.
>
> <MESSAGE> 요소와 같이 사용하는 경우는 <MESSAGE> 요소가 우선적으로 처리되어 <RESULT> 요소에서 설정한 MESSAGE 속성은 무시 된다.

- **속성**

|         |                  |
|:-------:|:----------------:|
|  속성   |      설 명       |
|  CODE   |  처리 결과 코드  |
| MESSAGE | 처리 결과 메시지 |

- **Example**

```
<!--조회 시 사용하기-->
<?xml version="1.0" ?>
<SHEET>
<DATA>
(조회된 데이터 중략)
</DATA>
<RESULT CODE="0" MESSAGE="조회가 완료되었습니다."></RESULT>
</SHEET>
```

- **제공 버전**

> **7.0.0.0**### 6.1.2 저장 XML

> 저장 함수를 통해 읽어들이는 XML 전체 구조는 다음과 같다.

```
<!—전체 처리 결과를 가져오는 경우 🡪
<?xml version='1.0' ?>
<SHEET>
<!—선택항목. ETC-DATA 요소 🡪

<ETC-DATA>

<ETC KEY="key_name">key_value</ETC>

</ETC-DATA>
<!—필수항목. RESULT 요소 🡪
<RESULT CODE="0"
MESSAGE="완료 후 메시지">
</RESULT>
</SHEET>
<!—각 행단위 트랜잭션 결과의 경우 🡪
<?xml version='1.0' ?>
<SHEET>
<!—선택항목. ETC-DATA 요소 🡪

<ETC-DATA>

<ETC KEY="key_name">key_value</ETC>

</ETC-DATA>
<!—필수항목. RESULT 요소 🡪
<RESULT>
<TR>
<TD>OK</TD>
<TD>DUP</TD>
<TD>MISS</TD>
<TD>NO</TD>
</TR>
</RESULT>
</SHEET>
```

> 위의 저장 XML에서 사용하는 XML요소는 다음과 같이 필수 항목과 선택 항목으로 나누어 진다.

|          |          |                           |
|:--------:|:--------:|:-------------------------:|
|  요소명  | 필수여부 |           설 명           |
|  SHEET   |   필수   | 저장 데이터의 최상위 요소 |
|  RESULT  |   필수   |  저장 데이터의 결과 요소  |
| ETC-DATA |   선택   |   기타 데이터 설정 요소   |### 6.1.2.1 SHEET 요소

> 저장 데이터의 최상위를 의미 한다.
>
> 이 요소는 저장 XML의 최 상위 요소로 XML 기본 정의 아래 반드시 하나만 사용해야 한다. 이 요소 안에 사용되는 <RESULT> 요소는 저장 결과 데이터를 의미하며 단 하나만 사용해야 한다. <ETC-DATA> 요소는 조회된 데이터 이외의 기타 데이터를 가져오는 요소로 여러 개 사용 할 수 있다.

- **속성**

| 속성  | 설 명 |
| --- | --- |
| 없음  |     |

- **Example**

```
<!—저장 성공의 경우 🡪
<?xml version="1.0" ?>
<SHEET>
<RESULT CODE="0" MESSAGE="정상적으로 처리되었습니다. ">
</SHEET>
<!—저장 실패의 경우 🡪
<?xml version="1.0" ?>
<SHEET>
<RESULT CODE="-1" MESSAGE="저장에 실패하였습니다.">
</SHEET>
```

- **제공 버전**

> **7.0.0.0**### 6.1.2.2 RESULT 요소

> 저장 데이터의 결과를 의미 한다.
>
> CODE 속성은 저장 처리 결과에 대한 코드 이며 정수값을 설정 한다.
>
> 설정 값이 0 이상인 경우 정상 처리로 모든 트랜잭션 상태의 행을 업데이트 처리한다. 설정 값이 0보다 작은 경우는 실패 처리로 결과에 대한 업데이트는 처리 하지 않고 현재 트랜잭션 상태를 그대로 유지한다.
>
> MESSAGE 속성은 처리 결과에 대한 메시지를 설정한다.
>
> 이 속성을 설정 한 경우 OnSaveEnd 이벤트의 인자로 전달된다.

- **속성**

|         |                  |
|:-------:|:----------------:|
|  속성   |      설 명       |
|  CODE   |  처리 결과 코드  |
| MESSAGE | 처리 결과 메시지 |

- **Example**

```
<!—저장 성공의 경우 🡪
<?xml version="1.0" ?>
<SHEET>
<RESULT CODE="0" MESSAGE="정상적으로 처리되었습니다.">
</SHEET>
<!—저장 실패의 경우 🡪
<?xml version="1.0" ?>
<SHEET>
<RESULT CODE="-1" MESSAGE="저장에 실패하였습니다.">
</SHEET>
```

- **제공 버전**

> **7.0.0.0**
>
> **  **### 6.1.2.3 TR 요소

> 저장 완료된 데이터의 트랜잭션 결과를 의미한다.
>
> 이 요소는 RESULT 요소 안에 사용되며, 각 행단위 트랜잭션 결과를 묶어 놓은 요소로 이 요소 안에 사용되는 TD 요소가 각 행단위의 결과를 의미한다.

- **속성**

| 속성  | 설 명 |
| --- | --- |
| 없음  |     |

- **Example**

```
<?xml version='1.0' ?>
<SHEET>
<RESULT>
<TR>
<TD>OK</TD>
<TD>DUP</TD>
<TD>MISS</TD>
<TD>NO</TD>
</TR>
</RESULT>
</SHEET>
```

- **제공 버전**

> **7.0.0.0**
>
> **  **### 6.1.2.4 TD 요소

> 각 행의 트랜잭션 결과를 의미한다.
>
> 이 요소는 TR 요소안에 사용되며 각 행의 트랜잭션 결과를 의미한다. 따라서 트랜잭션 개수가 3개라면 이 요소도 3번 반복 사용해야 한다.
>
> 트랜잭션 결과는 다음과 같이 처리된다.

| 결과   | 사용예      | 처리결과    |          |               |
| ---- | -------- | ------- | -------- | ------------- |
| 결과   | 사용예      | 상태      | 상태값 변경   | Result 컬럼 표시값 |
| OK   | **OK**   | "입력"일 때 | 조회상태로 변경 | "입력완료" 표시     |
| OK   | **OK**   | "수정"일 때 | 조회상태로 변경 | "수정완료" 표시     |
| OK   | **OK**   | "삭제"일 때 | 행이 사라짐   | 없음            |
| OK   | **OK**   | 그외 일 때  | 조회상태로 변경 | "저장완료" 표시     |
| DUP  | **DUP**  | 무관      | 변경 없음    | "저장중복" 표시     |
| MISS | **MISS** | 무관      | 변경 없음    | "미처리" 표시      |
| NO   | **NO**   | 무관      | 변경 없음    | "저장오류" 표시     |

- Result 컬럼 표시 값은 ibmsg 에서 변경하여 사용할 수 있다.

<!-- -->

- **속성**

| 속성  | 설 명 |
| --- | --- |
| 없음  |     |

- **Example**

```
<?xml version='1.0' ?>
<SHEET>
<RESULT>
<TR>
<TD>OK</TD>
<TD>DUP</TD>
<TD>MISS</TD>
<TD>NO</TD>
</TR>
</RESULT>
</SHEET>
```

- **제공 버전**

> **7.0.0.0**### 6.1.2.5 ETC-DATA 요소

> 6.1.1.5 ETC-DATA 요소 참조