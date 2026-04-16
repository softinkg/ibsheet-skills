# LoadExcelBuffer Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > LoadExcelBuffer Method

---

- **기능**

> 1개의 엑셀 문서로부터 여러 개의 시트에 로딩한다.
>
> LoadExcelBuffer 의 IsBuffer 인자를 true 로 설정하면 이후로 실행되는 LoadExcel은 실제로 동작하지 않으며 모두 내부 메모리에 버퍼링된다.
>
> 이후에 LoadExcelBuffer 의 IsBuffer 인자를 false 로 설정하는 순간 파일 업로드 창이 뜨게된다.
>
> 버퍼링되는 동안 지정되는 FileExt 속성은 제일 마지막에 설정된 값이 유효하다.

- **Syntax**

|        |                                     |
|:------:|-------------------------------------|
| Syntax | ObjId.**LoadExcelBuffer**(IsBuffer) |

- **Info**

|           |      |          |             |
|:---------:|:----:|:--------:|:-----------:|
| Parameter | Type | 필수여부 |    설 명    |
| IsBuffer  | bool |   필수   | 버퍼링 여부 |

- **Example**

```javascript
// 엑셀 파일 즉시 로딩하기
mySheet.LoadExcel();
//이후로는 버퍼링한다. 아무 동작 안함.
mySheet.LoadExcelBuffer(true);
// mySheet에 엑셀파일의 첫번째 시트의 헤더타이틀을 서로 비교하여 동일한 컬럼끼리 로딩을 하되 7행부터 9 행까지만 로딩하기로 예약함
mySheet.LoadExcel({Mode:'HeaderMatch',StartRow:'7',EndRow:'9', WorkSheetNo:1});
// mySheet2에 엑셀파일의 두번째 시트를 IBSheet의 첫번째 컬럼에 엑셀의 5번째 컬럼의 값을 로딩하고, IBSheet 의 5번째 컬럼에 엑셀의 1번째 컬럼의 값을로딩하기로 예약함
mySheet2.LoadExcel({ColumnMapping:'5|4|3|2|1', WorkSheetNo:2});
// 버퍼링된 모든 엑셀 로딩 자료와 파일을 서버로 보내기 위해 파일 업로드창을 띄운다
mySheet.LoadExcelBuffer(false);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **