# Down2ExcelBuffer Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > Down2ExcelBuffer Method

---

- **기능**

> 여러 개의 시트로부터 1개의 엑셀 문서로 다운로드 받는다.
>
> Down2ExcelBuffer 의 buffer 인자를 true 로 설정하면 이후로 실행되는Down2Excel은 실제로 동작하지 않으며 모두 내부 메모리에 버퍼링된다.
>
> 이후에 Down2ExcelBuffer 의 buffer 인자를 false 로 설정하는 순간 버퍼링된 모든 시트들을 하나의 엑셀 파일안에 시트별로 각각의 워크시트에 저장되어 다운로드 된다.
>
> 버퍼링되는 동안 지정되는 엑셀 파일명칭은 최초에 설정된 파일명 및 엑셀 파일 포맷이 유효하며, 워크시트명이 고유하지 않고 중복될 경우 자동적으로 괄호가 부여되어 다운로드 된다.
>
> Down2ExcelBuffer 를 true로 설정하고 DirectDown2Excel을 호출하여 여러개의 시트를 하나의 엑셀 파일에 DirectDown2Excel 로 다운로드 할 수 있다.
>
> 시트에서의 호출방법은 Down2Excel과 동일하며 URL 인자는 모두 동일 페이지를 설정해야 한다.
>
> 데이터를 처리하는 jsp 파일에서는 DirectDown2Excel 을 호출한 시트 순서에 맞게 데이터를 생성하여 "SHEETDATA" 뒤에 1부터 일련번호를 붙여서 setAttribute 처리한다. 이때 첫번째 시트는 일련번호 없이 "SHEETDATA" 로 설정하고, 두번째 시트 이후부터 일련번호를 붙여서 설정해주면 된다.

- **Syntax**

|        |                                      |
|:------:|--------------------------------------|
| Syntax | ObjId.**Down2ExcelBuffer**(IsBuffer) |

- **Info**

|           |      |          |             |
|:---------:|:----:|:--------:|:-----------:|
| Parameter | Type | 필수여부 |    설 명    |
| IsBuffer  | bool |   필수   | 버퍼링 여부 |

- **Example**

```
//이후로는 버퍼링한다. 아무 동작 안함.
firstSheet.Down2ExcelBuffer(true);
// 첫번째 워크시트에 담아두기를 예약함.
firstSheet.Down2Excel({FileName:'excel2',SheetName:'sheet1'});
// 두번째 워크시트에 담아두기를 예약함.
secondSheet.Down2Excel({FileName:'excel2',SheetName:' sheet2'});
// 버퍼링된 모든 엑셀 자료를 1개의 엑셀문서에 모두 모아서 즉시 다운로드 한다.
firstSheet.Down2ExcelBuffer(false);
```

> DirectDown2Excel 로 여러개의 시트를 다운로드 하는 경우

```
// 시트에서 Down2ExcelBuffer 통해 DirectDown2Excel 호출
firstSheet.Down2ExcelBuffer(true);
firstSheet.DirectDown2Excel({URL:"../jsp/fp.jsp",FileName:"IBLeaders.xls"});
secondSheet.DirectDown2Excel({URL:"../jsp/fp.jsp",FileName:"IBLeaders.xls", SheetDesign:1});
firstSheet.Down2ExcelBuffer(false);
// 데이터 생성 파일 (fp.jsp)
request.setAttribute("SHEETDATA", li);
request.setAttribute("SHEETDATA1", li2);
```

- **제공 버전**

> **7.0.0.0  **