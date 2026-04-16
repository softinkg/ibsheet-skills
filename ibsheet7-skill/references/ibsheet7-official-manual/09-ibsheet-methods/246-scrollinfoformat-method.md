# ScrollInfoFormat Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ScrollInfoFormat Method

---

- **기능**

> 세로 스크롤 지연 처리 시간동안 표시되는 메시지 포멧을 설정하거나 확인 한다. 설정 시 아래의 예약어와 컬럼 정보의 조합으로 일반 텍스트 형식과 간단한 마크업 태그 형식으로 설정 할수 있다. 마크업 태그 형식으로 설정시 복잡도에 따라 성능에 영향을 줄 수 있기 때문에 가급적이면 간단한 형식으로 사용하여야 한다. 사용 가능한 예약어는 아래와 같으며, 별도 설정이 없는 경우 기본값인 "TOPROW / TOTALROWS" 로 처리 된다.

| 예약어                   | 설명                                                                             |
| --------------------- | ------------------------------------------------------------------------------ |
| TOTALROWS             | 전체 건수                                                                          |
| TOPROW                | 스크롤 이동시 상단에 위치할 행의 Index                                                       |
| 컬럼의 Index 또는 SaveName | TOPRow 의 해당 컬럼의 셀 정보 컬럼정보 사용시 해당 값의 앞뒤에 "\|" 문자를 사용하여야 한다. (예) \|3\|, \|sText} |
| TOPROW2               | 실제로 보이는 행의 Index (소계, 누계, 히든 제외)                                               |
| TOTALROWS2            | 전체 건수(소계/누계 제외)                                                                |
| ROWVIEWCOUNT          | 전체 건수(숨겨진 행 제외)                                                                |
| DATAROWVIEWCOUNT      | 전체 건수 (소계/누계와 숨겨진 행 제외)                                                        |

- **Syntax**

|        |     |                                 |
|:------:|:---:|---------------------------------|
| Syntax | Get | ObjId.**GetScrollInfoFormat**() |

- **Info**

> **Return**: String, 현재 설정값

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//현재 설정되어있는 스크롤 정보 메시지 포맷을 확인 한다.
Console.log("ScrollInfoFormat :", mySheet.GetScrollInfoFormat());
```

- **Syntax**

|        |     |                                       |
|:------:|:---:|---------------------------------------|
| Syntax | Set | ObjId.**SetScrollInfoFormat**(Format) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명            |
| --------- | ------ | ---- | -------------- |
| Format    | String | 필수   | 설정할 메시지 포맷 문자열 |

- **Example**

```javascript
// 기본값에 컬럼인덱스 3번의 셀 정보 표시 설정
mySheet.SetScrollInfoFormat("[TOPROW / TOTALROWS] |3|");
// 기본값에 컬럼의 SaveName이 "sName"인 셀 정보 표시 설정
mySheet.SetScrollInfoFormat("[TOPROW / TOTALROWS] |sName|");
// 간단안 마크업 태그를 이용한 설정 (셀 정보에 blue 색상 적용)
var format = "[TOPROW / TOTALROWS] <font color='blue'>|sName|</font>";
mySheet.SetScrollInfoFormat(format);
```

- **제공 버전**

| **7.0.13.11** |     |
|---------------|-----|

> **  **