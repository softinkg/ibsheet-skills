# ShowFooterRow Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ShowFooterRow Method

---

- **기능**

> 그리드 하단에 고정되는 사용자 정의 행을 설정한다.
>
> \`data\` 인자는 JSON 형식의 조회 데이터 구조를 사용한다.
>
> 형식은 Key:Value 형태이며, Key는 컬럼 초기화 구성시 설정한 SaveName 이며 Value는 해당 셀의 값이 된다.
>
> 속성은 Key 값을 초기화시 설정된 SaveName과 속성명을 '#' 으로 구분하여 구성해서 사용한다. (예, SaveName#Type)
>
> \`Type\` 은 \`Text\`, \`Int\`, \`Float\` 의 데이터타입만 허용되고, 기타 속성에 대한 타입 및 설정은 InitColumns Method 의 속성 설명을 참고 한다.

- **Syntax**

|        |                               |
|:------:|-------------------------------|
| Syntax | ObjId.**ShowFooterRow**(Data) |

- **Info**

> **Return**: None

| Parameter | Type          | 필수여부 | 설 명          |
| --------- | ------------- | ---- | ------------ |
| Data      | Object/ Array | 필수   | Footer 설정 객체 |

> 셀별 속성 설정은 해당 키값 과 속성명을 "#"으로 구분하여 사용하며 사용 가능한 속성은 다음과 같다 (예, SaveName#BackColor)

|                   |                                           |
|:-----------------:|:-----------------------------------------:|
|    **속성명**     |                 **설 명**                 |
|     **Type**      |   데이터 타입 (Text, Int, Float, Html)    |
|     **Align**     |               좌우 정렬 값                |
|    **RowSpan**    |              RowSpan 범위 값              |
|    **ColSpan**    |              ColSpan 범위 값              |
|   **FontColor**   |                 폰트색상                  |
|   **FontBold**    |                 폰트볼드                  |
|   **BackColor**   |                 셀 배경색                 |
|    **Format**     |                 포멧설정                  |
| **MultiLineText** |             셀 개행 처리 설정             |
|  **PointCount**   | 실수 형태의 데이터 타입에서 소수점 자리수 |

- **Example**

```
// 하단 고정행을 2개로 만들며, TEXT_DATA 컬럼의 경우 2행, 2열의 머지를 한 형태로 행을 생성함.
mySheet.ShowFooterRow([
{"SEQ":"순번", "SEQ#Type":"Int", "TEXT_DATA":"홍길동", "TEXT_DATA#BackColor":"blue", "TEXT_DATA#Align":"Center", "TEXT_DATA#RowSpan":2, "TEXT_DATA#ColSpan":2, "IMAGE_DATA":"이미지", "PASS_DATA":"비밀번호", "RADIO_DATA":"라디오"},
{"SEQ":"순번2", "COMBO_DATA":"콤보2","COMBOEDIT_DATA":"콤보에디트2", "DATE_DATA":"날짜2","CHECKBOX_DATA":"체크박스2","RADIO_DATA":"라디오2"}
]);
//sCenterName 셀의 경우 개행처리 허용 및 ColSpan 설정
mySheet.ShowFooterRow(
{"SEQ": "운영형태","SEQ#ColSpan": 2, "sCenterName#Type": "Text",
"sCenterName#MultiLineText": 1, "sCenterName": "직영 10곳, 공단위탁 \n 15곳, 민간위탁 1곳, 위탁 1곳", "sCenterName#ColSpan": 2, "sZip": "시설별 평균면적" })
```

- **제공 버전**

|   7.0.13.60    |                         |
|:--------------:|-------------------------|
| **7.0.13.141** | MultiLineText 속성 추가 |
| **7.0.13.158** | Html 타입 추가.         |