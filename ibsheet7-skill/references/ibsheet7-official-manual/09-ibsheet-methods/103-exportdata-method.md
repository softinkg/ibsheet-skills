# ExportData Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ExportData Method

---

- **기능**

> 시트내의 데이터를 json,xml,csv 형식으로 추출한다.
>
> 옵션을 통해 지정한 컬럼만 추출도 가능하다.

```
<?xml version="1.0" encoding="UTF-8" ?><data>

<row>

<COLSAVENAME1><![CDATA[data....]]></COLSAVENAME1>

<COLSAVENAME2><![CDATA[data....]]></COLSAVENAME2>

.....
</row>

</data>
```

> [xml 형식 추출]

```
{"data":[
{" COLSAVENAME1": data," COLSAVENAME2":"data2"...}
....
]}
```

> [json 형식 추출]

| "data1,data2,.....\r\n...." |
|-----------------------------|

> [csv형식 추출]

- **Syntax**

|        |                            |
|:------:|----------------------------|
| Syntax | ObjId.**ExportData**(info) |

- **Info**

> **Return**: Type으로 지정한 형식의 데이터

| Parameter          | Type    | 필수여부 | 설 명                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |     |
| ------------------ | ------- | ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| info.Type          | String  | 필수   | json,xml,csv 중에 하나 선택                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |     |
| info.Cols          | String  | 선택   | 추출할 컬럼(Default:모든컬럼)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |     |
| info.FormattedText | boolean | 선택   | 포멧이 적용된 문자열형식으로 추출할지 여부(Default:0)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |     |
| info.StyleProperty | boolean | 선택   | 추출데이터에 편집여부,배경색,글자색에 대한 데이터도 포함할 지 여부(json 형식인 경우에만 사용가능) \| 대상   \| 속성            \| 설명           \| \| ---- \| ------------- \| ------------ \| \| Row  \| Edit          \| 행 편집여부       \| \| Row  \| BackColor     \| 행 배경색        \| \| Row  \| FontColor     \| 행 글자색        \| \| Cell \| Edit          \| 셀 편집여부       \| \| Cell \| BackColor     \| 셀 배경색        \| \| Cell \| FontColor     \| 셀 글자색        \| \| Cell \| FontBold      \| 셀 글자 굵기      \| \| Cell \| FontItalic    \| 셀 글자 intalic \| \| Cell \| FontStrike    \| 셀 글자 strike  \| \| Cell \| FontUnderline \| 셀 글자 밑줄      \| |     |

- **Example**

```javascript
var param = {"Type":"json","Cols":"0|2|3|4"};
var json = mySheet.ExportData(param);
```

- **제공 버전**

> **7.0.13.21  
> 7.0.13.44 (FormattedText , StyleProperty 추가)**
>
> **  **