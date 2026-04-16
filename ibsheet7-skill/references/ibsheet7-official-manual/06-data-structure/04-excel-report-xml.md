# 6.4 엑셀리포트 XML

> **IBSheet7 개발자 가이드** > 데이터 구조 > 6.4 엑셀리포트 XML

---

> 엑셀 다운로드 함수(Down2Excel Method, DirectDown2Excel Method)를 통해 엑셀로 내릴 때 엑셀의 요지나 머리글 바닥글과 같이 엑셀에 대한 속성을 설정한다.

```
<?xml version='1.0' ?>
<Excel>
<!-- IBSheetSet 요소 -->
<IBSheetSet>
<StartRow>6</StartRow>
<Data>조회한 데이터</Data>
</IBSheetSet>
<!-- PageSet 요소 -->
<PageSet>
<PaperSize>A4</PaperSize>
<Orientation>Portrait</Orientation>
<CenterOnPage Horizontal="True" Vertical="False"/>
<RowsRepeat Row1="1" Row2="1" />
<ColsRepeat Col1="1" Col2="1" />
<DefaultRowHeight>18</DefaultRowHeight>
(중략)
</PageSet>
<!-- ColumnWidth 요소 -->
<ColumnWidth Col1="1" Col2="End">20</ColumnWidth>
<!-- RowHeight 요소 -->
<RowHeight Row1="5" Row2="6">30</RowHeight>
<!-- CustomHeader 요소 -->
<CustomHeader>
<LeftSection>(중략)</LeftSection>
<CenterSection>(중략)</CenterSection>
<RightSection>(중략)</RightSection>
</CustomHeader>
<!-- CustomFooter 요소 -->
<CustomFooter>
<LeftSection>(중략)</LeftSection>
<CenterSection>(중략)</CenterSection>
<RightSection>(중략)</RightSection>
</CustomFooter>
<!-- Label 요소 -->
<Label>
<Range Row1="5" Col1="1" Row2="4" Col2="10"> (중략) </Range>
</Label>
<!-- DataPattern 요소 -->
<DataPattern>
<Standard SheetCol="0" Word="소계*">(중략)
<Range Row1="5" Col1="1" Row2="4" Col2="10">(중략)</Range>
</Standard>
</DataPattern>
<!-- BorderSet 요소 -->
<BorderSet>
<Range Row1="5" Col1="1" Row2="4" Col2="10" >(중략)</Range>
</BorderSet>
</Excel>
```

> 위의 엑셀리포트XML에서 사용하는 XML 요소는 다음과 같다.

| 요소명 | 설명 |
|:--:|----|
| IBSheetSet 요소 | 엑셀에 내릴 IBSheet 부분을 설정, 이부분은 필수이고, 반드시 맨 처음 설정해야 함 |
| PageSet 요소 | 엑셀의 페이지 설정 |
| ColumnWidth 요소 | 엑셀의 컬럼 너비 설정 |
| RowHeight 요소 | 엑셀의 행의 높이 설정 |
| CustomHeader 요소 | 엑셀의 용지 설정의 머리글 설정 |
| CustomFooter 요소 | 엑셀의 용지 설정의 바닥글 설정 |
| Label 요소 | 엑셀의 셀에 표시할 문자열 설정 |
| DataPattern 요소 | 엑셀에서 기준 글자를 찾아 일정한 패턴을 설정 |
| BorderSet 요소 | 엑셀의 영역별 테두리 설정 |### 6.4.1 IBSheetSet 요소

> 엑셀파일에 설정될 IBSheet 부분을 의미한다.
>
> IBSheetSet 요소 하단에 사용하는 StartRow 요소는 Sheet의 데이터를 엑셀로 내릴 때 엑셀의 시작 행의 위치를 설정하며, 엑셀은 Sheet와 달리 첫 행을 1부터 시작한다.
>
> IBSheetSet 요소는 Label 요소를 사용할 경우 반드시 설정해야 하고, Excel 요소 바로 아래 최상단에 설정한다.

- **하위요소**

|              |                                             |
|:------------:|:-------------------------------------------:|
|     속성     |                    설 명                    |
| <StartRow> | Sheet의 데이터를 표시할 엑셀의 시작 행 위치 |

- **Example**

```
<?xml version="1.0" ?>
<Excel>
<IBSheetSet>
<StartRow>6</StartRow>
</IBSheetSet>
</Excel>
```

- **제공 버전**

> **7.0.0.0**### 6.4.2 PageSet 요소

> 엑셀 파일에 페이지 설정 부분을 의미한다.
>
> PageSet 요소는 엑셀 파일의 메뉴에서 "파일 > 페이지설정" 부분과 거의 흡사하다. 페이지에 대해서 설정해야 하는 각종 속성을 설정한다.

- **하위요소**

|  |  |
|:--:|:--:|
| 속성 | 설 명 |
| <PaperSize> | 엑셀의 용지 크기 설정 |
| <Orientation> | 엑셀의 용지 방향 설정 |
| <Margins> | 엑셀의 여백 설정 |
| <Scaling> | 엑셀의 용지 배율 설정 |
| <[CenterOnPage](mk:@MSITStore:D:\SVN\제품배포\IB%20Sheet%20Pro\IBSheet(A)\doc\3.x.x.x\IBSheet3.2.0.2.chm::/xml/excel_pageset_element.html#CenterOnPage)> | 엑셀의 페이지의 가운데에 대한 설정 |
| <[RowsRepeat](mk:@MSITStore:D:\SVN\제품배포\IB%20Sheet%20Pro\IBSheet(A)\doc\3.x.x.x\IBSheet3.2.0.2.chm::/xml/excel_pageset_element.html#RowsRepeat)> | 엑셀의 반복 행 설정 |
| <[ColsRepeat](mk:@MSITStore:D:\SVN\제품배포\IB%20Sheet%20Pro\IBSheet(A)\doc\3.x.x.x\IBSheet3.2.0.2.chm::/xml/excel_pageset_element.html#RowsRepeat)> | 엑셀의 반복 컬럼 설정 |
| <[DefaultRowHeight](mk:@MSITStore:D:\SVN\제품배포\IB%20Sheet%20Pro\IBSheet(A)\doc\3.x.x.x\IBSheet3.2.0.2.chm::/xml/excel_pageset_element.html#DefaultRowHeight)> | 엑셀의 기본 행 높이 설정 |
| <[DefaultFont](mk:@MSITStore:D:\SVN\제품배포\IB%20Sheet%20Pro\IBSheet(A)\doc\3.x.x.x\IBSheet3.2.0.2.chm::/xml/excel_pageset_element.html#DefaultFont)> | 엑셀의 기본 글꼴 설정 |

> PageSet 요소 하단의 PaperSize 요소는 페이지의 용지 크기를 설정하는 것으로 "A3, A4, B4, B5" 중 하나를 선택하여 설정하도록 한다. 기본은 "A4"이다.
>
> PageSet 요소 하단의 Orientation 요소는 용지의 방향을 설정하는 것으로 세로인 경우 "Portrait"로 설정하고, 가로인 경우 "Landscape"로 설정한다. 기본은 세로이다.
>
> PageSet 요소 하단의 Margins 요소는 용지의 여백을 설정하는 것으로 요소의 속성으로 여백을 설정한다. 기본은 엑셀의 기본 설정에 따라 설정된다.
>
> PageSet 요소 하단의 Scaling 요소는 용지의 배율을 설정하는 것으로 엑셀의 "축소/확대 배율"을 사용하는 경우와 "자동맞춤"을 사용하는 경우에 따라 "True","False"로 설정한다. "자동맞춤"을 사용하는 경우 "용지너비"와 "용지높이"를 엑셀에서 설정할수 있는 값으로 설정한다. 기본은 "축소/확대 배율"을 사용는 것이다.
>
> PageSet 요소 하단의 CenterOnPage 요소는 페이지의 가운데에 대한 설정하는 것으로 가로로 가운데로 설정시 Horizontal 속성을 "true"로 설정하고, 세로로 가운데로 설정 시 Vertical 속성을 "true"로 설정한다. 기본은 둘 다 "false"이다.
>
> PageSet 요소 하단의 RowsRepeat 요소는 반복 행에 대한 설정하는 것으로 시작 행을 Row1 속성에 마지막 행은 Row2 속성에 설정한다. 만약 1개 행만 반복하고자 하는 경우 Row2는 설정하지 않아도 된다. 기본은 반복 행이 없다.
>
> PageSet 요소 하단의 ColsRepeat 요소는 반복 컬럼에 대한 설정하는 것으로 시작 컬럼을 Col1 속성에 마지막 컬럼은 Col2 속성에 설정한다. 만약 1개 컬럼만 반복하고자 하는 경우 Col2는 설정하지 않아도 된다. 기본은 반복 컬럼이 없다.
>
> PageSet 요소 하단의 DefaultRowHeight 요소는 엑셀 각 행의 기본 높이를 설정하는 것으로 기본은 13.5이다.
>
> PageSet 요소 하단의 DefaultFont 요소는 페이지의 기본 글꼴을 설정한다.
>
> Name 속성은 글꼴, Bold 속성은 굵기, Italic 속성은 기울림 여부, size 속성은 글자 크기, UnderLine은 밑줄로 "None \| Single \| Double"중 선택한다. Strikethrough 속성은 취소선 사용 여부, Superscript 속성은 위첨자 사용 여부, Superscript 속성은 아래첨자 사용 여부, Color 글자색상을 설정한다.

- **Example**

```
<?xml version="1.0" ?>
<Excel>
<PageSet>
<PaperSize>A4</PaperSize>
<Orientation>Landscape</Orientation>
<Margins Top="1.5" Header="1.3" Left="1" Right="1" Bottom="1.5" Footer="1.3" >True</Margins>
<Scaling>
<Adjust Value="100">true</Adjust>
<Fit Height="1" Width="1">false</Fit>
</Scaling>
<RowsRepeat Row1="6" Row2="6">True</RowsRepeat>
<ColsRepeat Col1="1" Col2="1">False</ColsRepeat>
<DefaultRowHeight>17</DefaultRowHeight>
<DefaultFont Name="돋움체" size="9"/>
</PageSet>
</Excel>
```

- **제공 버전**

> **7.0.0.0**### 6.4.3 ColumnWidth 요소

> 엑셀의 각 컬럼에 너비를 설정한다.
>
> 이 요소는 1개 컬럼 너비 뿐만 아니라 , 여러개 컬럼의 너비를 영역으로 설정할수 있다. 이 요소의 Col1 속성은 영역으로 컬럼너비를 설정할때 시작 컬럼의 번호이고, Col2 속성은 마지막 컬럼의 번호이다.
>
> 컬럼의 너비는 -1로 설정할 경우 엑셀이 모두 내려진 후 해당 컬럼의 가장 넓은 글자의 너비에 맞춰 자동으로 조정되는 설정이고, 일반적으로 엑셀에서 설정하는 컬럼 너비를 숫자로 설정한다.

- **속성**

|      |                                                     |
|:----:|:---------------------------------------------------:|
| 속성 |                        설 명                        |
| Col1 |      엑셀의 시작 컬럼 번호(엑셀은 1부터 시작)       |
| Col2 | 엑셀의 마지막 컬럼 번호, 마지막은 "End"로 설정 가능 |

- **Example**

```
<?xml version="1.0" ?>
<Excel>
<ColumnWidth Col1="1" Col2="End">-1</ColumnWidth>
<ColumnWidth Col1="8">10</ColumnWidth>
</Excel>
```

- **제공 버전**

> **7.0.0.0**### 6.4.4 RowHeight 요소

> 엑셀의 각 행에 높이를 설정한다.
>
> 이 요소는 1개 행 높이 뿐만 아니라 , 여러개 행의 높이를 영역으로 설정할수 있다. 이 요소의 Row1 속성은 영역으로 행높이를 설정할때 시작 행의 번호이고, Row2 속성은 마지막 행의 번호이다.

- **속성**

|      |                                                   |
|:----:|:-------------------------------------------------:|
| 속성 |                       설 명                       |
| Row1 |      엑셀의 시작 행 번호(엑셀은 1부터 시작)       |
| Row2 | 엑셀의 마지막 행 번호, 마지막은 "End"로 설정 가능 |

- **Example**

```
<?xml version="1.0" ?>
<Excel>
<RowHeight Row1="2" Row2="5">15</RowHeight>
<RowHeight Row1="6">5</RowHeight>
</Excel>
```

- **제공 버전**

> **7.0.0.0**### 6.4.5 CustomHeader 요소

> 엑셀의 페이지 설정의 머리글을 설정한다.
>
> 엑셀 메뉴에서 "파일 > 페이지설정"의 "머리글/바닥글" 설정 탭 중 "머리글 부분을 설정하는것이 이 요소이다.

- **하위요소**

|                   |                  |
|:-----------------:|:----------------:|
|       속성        |      설 명       |
|  <LeftSection>  |  왼쪽 구역 설정  |
| <CenterSection> | 가운데 구역 설정 |
| <RightSection>  | 오른쪽 구역 설정 |

- **Example**

```javascript
<?xml version="1.0" ?>
<Excel>
<!--머리글 설정하기-->
<CustomHeader>
<LeftSection>
<font Name="돋움체" Size="12"/>
<InputText><![CDATA[IB Leaders]]></InputText>
</LeftSection>
<RightSection>
<font Name="돋움체" Size="12"/>
<InputText><![CDATA[IBSheet 엑셀 리포트]]></InputText>
</RightSection>
</CustomHeader>
</Excel>
```

- **제공 버전**

> **7.0.0.0  **### 6.4.5.1 LeftSection, CenterSection, RightSection 요소

> 엑셀의 페이지의 머리글과 바닥글의 각 섹션을 설정한다.
>
> 이 요소들은 머리글 또는 바닥글의 각 영역에 표시할 글자나 이미지를 설정한다.

- **하위요소**

|               |                              |
|:-------------:|:----------------------------:|
|     속성      |            설 명             |
|   <Font>    |          글꼴 설정           |
| <InputText> | 해당 영역에 표시할 글자 설정 |

> 이 요소 하단에 Font 요소는 해당 영역의 글꼴을 설정한다. Font의 속성의 Name 속성은 글꼴, Bold 속성은 굵기, Italic 속성은 기울림 여부, size 속성은 글자 크기, UnderLine은 밑줄로 "None \| Single \| Double"중 선택한다.
>
> 이 요소 하단에 InputText 요소는 해당 영역의 표시할 글자를 설정한다. InputText요소의 PCDATA 영역에 표시하고 하는 글자를 다음 예약어와 함께 사용할 수 있다.

| &P    | &N     | &D    | &T  |
| ----- | ------ | ----- | --- |
| 페이지번호 | 전체페이지수 | 날짜    | 시간  |
| &F    | &A     | 문자열   |     |
| 파일명   | 워크시트명  | 표시문자열 |     |

- **Example**

```javascript
<?xml version="1.0" ?>
<Excel>
<!--머리글 설정하기-->
<CustomHeader>
<LeftSection>
<Font Name="돋움체" Size="12"/>
<InputText><![CDATA[&D]]></InputText>
</LeftSection>
<RightSection>
<Font Name="돋움체" Size="12"/>
<InputText><![CDATA[IBSheet 엑셀 리포트]]></InputText>
</RightSection>
</CustomHeader>
</Excel>
```

- **제공 버전**

> **7.0.0.0  **### 6.4.6 CustomFooter 요소

> 엑셀의 페이지 설정의 바닥글을 설정한다.
>
> 엑셀 메뉴에서 "파일 > 페이지설정"의 "머리글/바닥글" 설정 탭 중 "바닥글 부분을 설정하는것이 이 요소이다.

- **하위요소**

|                   |                  |
|:-----------------:|:----------------:|
|       속성        |      설 명       |
|  <LeftSection>  |  왼쪽 구역 설정  |
| <CenterSection> | 가운데 구역 설정 |
| <RightSection>  | 오른쪽 구역 설정 |

> 요소의 상세설명은 CustomHeader의 하단 요소 설명을 참조한다.

- **Example**

```
<?xml version="1.0" ?>
<Excel>
<!--바닥글 설정하기-->
<CustomFooter>
<CenterSection>
<Font Name="돋움체" Size="12"/>
<InputText><![CDATA[&P / &N]]></InputText>
</CenterSection>
</CustomFooter>
</Excel>
```

- **제공 버전**

> **7.0.0.0**
>
> **  **### 6.4.7 Label 요소

> 엑셀의 셀에 원하는 글자를 설정한다.
>
> 엑셀의 워크시트에 셀이라는 영역에는 다양한 글자를 설정할 수 있다. Sheet에서 자동으로 내리는 데이터는 "Excel 요소 > IBSheetSet 요소"에 의해서 가능하지만 그 외의 엑셀의 특정 영역(Range)에 글자를 쓰기 위해서는 이 요소를 사용한다.

- **하위요소**

|           |                                             |
|:---------:|:-------------------------------------------:|
|   속성    |                    설 명                    |
| <Range> | Label을 설정하는 엑셀의 셀 영역에 대한 요소 |

- **Example**

```
<Label>
<Range Row1="1" Col1="1" Row2="1" Col2="End" RowHeight="40">
<CellFormat>
<Merge>true</Merge>
<Alignment Horizontal="Center" Vertical="Center"/>
<Interior BackColor="255,255,133" Pattern="xlGray50" PatternColor="192,192,192"/>
<Font Name="굴림" Bold="True" Size="15" />
</CellFormat>
<InputText><![CDATA[모델별 용량 금액 리스트]]></InputText>
<BorderStyle>
<TopEdge Style="Continuous" Weight="Medium"/>
<BottomEdge Style="Continuous" Weight="Medium"/>
</BorderStyle>
</Range>
</Label>
```

- **제공 버전**

> **7.0.0.0**
>
> **  **### 6.4.7.1 Range 요소(Label 요소의 하위)

> Label 요소로 엑셀의 워크시트의 셀에 원하는 글자를 설정할때 셀 영역을 의미한다.
>
> 이 요소의 속성은 Row1, Row2는 엑셀의 행번호를 의미하며 엑셀은 행을 1부터 시작하므로 Sheet의 시작행과 동일하게 처리하면 안된다. Row1, Row2 인자를 행번호를 마지막 행번호 사용할 경우 "end"라는 글자로 설정할 수 있다.
>
> Col1, Col2 인자도 동일하게 1컬럼부터 시작하며, 마지막 컬럼을 사용할 경우 "end"라는 글자를 설정할수 있다.
>
> Label을 표시할 엑셀의 영역이 1개인 경우 Row1과 Col1 속성만 사용하고, Row2와 Col2 속성은 제외하고 사용할 수 있다.

- **속성**

|            |                                                       |
|:----------:|:-----------------------------------------------------:|
|    속성    |                         설 명                         |
|    Row1    |   Label을 설정할 엑셀 영역의 시작 행번호 또는 "End"   |
|    Col1    |  Label을 설정할 엑셀 영역의 시작 컬럼번호 또는 "End"  |
|    Row2    |  Label을 설정할 엑셀 영역의 마지막 행번호 또는 "End"  |
|    Col2    | Label을 설정할 엑셀 영역의 마지막 컬럼번호 또는 "End" |
| RowHeights |             엑셀 영역의 행높이, 픽셀단위              |

- **하위요소**

|                 |                                                          |
|:---------------:|:--------------------------------------------------------:|
|      속성       |                          설 명                           |
| <CellFormat>  | 엑셀 영역의 머지, 정렬, 색상이나 글꼴 등을 설정하는 요소 |
|  <InputText>  |         엑셀 영역에 표시할 글자를 설정하는 요소          |
| <BorderStyle> |           엑셀 영역에서 테두리를 설정하는 요소           |

- **Example**

```
<?xml version="1.0" ?>
<Excel>
<Label>
<Range Row1="3" Col1="end" Row2="3" Col2="end" RowHeight="15">
<CellFormat>
<Alignment Horizontal="Right" Vertical="Center"/>
<Font Name="굴림" Bold="True" Size="9" />
</CellFormat>
<InputText><![CDATA[단위 [원화:만원]]]></InputText>
</Range>
</Label>
</Excel>
```

- **제공 버전**

> **7.0.0.0**### 6.4.7.1.1 CellFomat 요소

> 엑셀 영역의 머지나 정렬, 색상, 글꼴 등을 설정한다.
>
> 이 요소는 부모인 Range 요소에서 선택한 엑셀의 셀 영역에 대한 각종 속성을 설정한다.

- **하위요소**

|               |                                       |
|:-------------:|:-------------------------------------:|
|     요소      |                 설 명                 |
|   <Merge>   | 엑셀의 셀 영역을 머지 할지 여부 설정  |
| <Alignment> |      엑셀의 셀 영역의 정렬 설정       |
| <Interior>  | 엑셀의 셀 영역의 배경 색 및 패턴 설정 |
|   <Font>    |      엑셀의 셀 영역의 글꼴 설정       |

> 이 요소 하단의 Merge 요소는 엑셀의 셀 영역을 머지할것인가 여부이며, 영역의 머지는 아래와 같이 "TRUE" 또는 "FALSE"로 설정한다. 기본을 "FALSE"이다
>
> 이 요소 하단의 Alignment 요소는 엑셀의 셀 영역의 가로 정렬과 세로 정렬을 설정한다. 가로 정렬은 "Horizandtal" 이고, 설정할 수 있는 값은 "Left", "Center", "Right"이다. 세로 정렬은 "Vertical"이고, 설정할 수 있는 값은 "Top", "Center", "Bottom" 이다.
>
> 이 요소 하단의 Interior 요소는 엑셀의 셀 영역의 색상이나 패턴을 설정한다. 엑셀에서 셀서식의 "무늬" 설정과 동일하며, 설정할수 있는 속성은 다음과 같다.

- **Interior 속성**

|  |  |
|:--:|:--:|
| 속성 | 설 명 |
| BackColor | 영역의 배경색을 설정한다. |
| PatternColor | 영역의 패턴색을 설정한다. |
| Pattern | 영영의 패턴을 설정한다. 패턴종류는 (xlSolid, xlGray75, xlGray50, xlGray25, xlGray16, xlGray8, xlHorizontal, xlVertical, xlDown, xlUp, xlChecker, xlSemiGray75, xlLightHorizontal, xlLightVertical, xlLightDown, xlLightUp, xlGrid, xlCrissCross) |

> 이 요소 하단에 Font 요소는 해당 영역의 글꼴을 설정한다. Font의 속성의 Name 속성은 글꼴, Bold 속성은 굵기, Italic 속성은 기울림 여부, size 속성은 글자 크기, UnderLine은 밑줄로 "None \| Single \| Double"중 선택한다.

- **Example**

```
<?xml version="1.0" ?>
<Excel>
<Label>
<Range Row1="3" Col1="end" Row2="3" Col2="end" RowHeight="15">
<CellFormat>
<Alignment Horizontal="Right" Vertical="Center"/>
<Font Name="굴림" Bold="True" Size="9" />
</CellFormat>
<InputText><![CDATA[단위 [원화:만원]]]></InputText>
</Range>
</Label>
</Excel>
```

- **제공 버전**

> **7.0.0.0**### 6.4.7.1.2 InputText 요소

> 엑셀 영역에 표시할 글자를 설정한다.
>
> 이 요소는 부모인 Range 요소에서 선택한 엑셀의 셀 영역에 글자를 표시한다.
>
> 이때 주의할 점은 표시하는 글자 중에 특수문자(&, <, >, ', ") 가 있는 경우 변환문자로 변환하거나 CDATA Section을 사용한다.
>
> 줄바꿈 글자를 설정할때 "\n"을 포함하여 설정한다.

- **Example**

```
<?xml version="1.0" ?>
<Excel>
<Label>
<Range Row1="3" Col1="end" Row2="3" Col2="end" RowHeight="15">
<InputText><![CDATA[단위 [원화:만원]]]></InputText>
</Range>
</Label>
</Excel>
```

- **제공 버전**

> **7.0.0.0**
>
> **  **### 6.4.7.1.3 BorderStyle 요소

> 엑셀 영역에 테두리 선을 설정한다.
>
> 이 요소는 Range 요소 하단에 사용되며, Range 요소에서 선택된 영역에 테두리를 설정한다. 이 요소 하단에 사용되는 각 요소인 TopEdge 요소, BottomEdge 요소, LeftEdge 요소, RightEdge 요소 등의 요소 들은 Style, Weight, Color 속성을 각각 갖는다.

- **Style 속성**

|            |            |        |                 |
|:----------:|:----------:|:------:|:---------------:|
|   선없음   |   연속선   |  대쉬  |     대쉬+점     |
|    None    | Continuous |  Dash  |     DashDot     |
| 대쉬+점+점 |    점선    | 이중순 | 기울어진대쉬+점 |
| DashDotDot |    Dot     | Double |  SlantDashDot   |

- **Wieght 속성**

|            |        |            |        |
|:----------:|:------:|:----------:|:------:|
| 매우가는선 | 가는선 | 중간굵은선 | 굵은선 |
|  Hairline  |  Thin  |   Medium   | Thick  |

> Color 속성은 원하는 색상을 RGB의 구조로 설정한다.

- **Example**

```
<?xml version="1.0" ?>
<Excel>
<Label>
<Range Row1="3" Col1="1" Row2="3" Col2="end" RowHeight="15">
<InputText>표시글자</InputText>
<BorderStyle>
<TopEdge Style="Dash" Weight="Medium" Color="255,0,0"/>
<BottomEdge Style="Dash" Weight="Medium" Color="0,0,0"/>
<LeftEdge Style="Continuous" Weight="Hairline" Color="0,0,255"/>
<RightEdge Style="Continuous" Weight="Hairline" Color="0,0,0"/>
</BorderStyle>
</Range>
</Label>
</Excel>
```

- **제공 버전**

> **7.0.0.0**### 6.4.8 DataPattern 요소

> Sheet에서 내려진 데이터의 기준 글자를 찾아 엑셀 영역에 일정 패턴을 설정한다.
>
> Sheet에서 내리지는 데이터는 "Excel 요소 > IBSheetSet 요소"에 의해서 엑셀의 x 번째 행부터 내려진다.
>
> 이렇게 Sheet에서 내려진 데이터의 특정 컬럼에 해당하는 데이터가 기준에 맞을때 이 요소에서 설정된 일정 패턴을 적용한다.

- **하위요소**

|              |                                         |
|:------------:|:---------------------------------------:|
|     속성     |                  설 명                  |
| <Standard> | 패턴을 설정할 데이터의 기준을 설정한다. |

- **Example**

```
<?xml version="1.0" ?>
<Excel>
<DataPattern>
<Standard SheetCol="0" Word="소계*">
<Range Col1="1" Col2="End" RowHeight="25">
<CellFormat> (중략) </CellFormat>
<BorderStyle> (중략) </BorderStyle>
</Range>
</Standard>
</DataPattern>
</Excel>
```

- **제공 버전**

> **7.0.0.0**### 6.4.8.1 Standard 요소

> 패턴을 설정하는 기준 글자의 기준을 설정한다.
>
> Sheet에서 내려진 데이터에 일정한 패턴을 설정하는데, 이때 이 요소는 기준이 되는 정보를 설정한다.
>
> SheetCol 속성은 엑셀에 내려지는 Sheet 데이터 중 기준을 설정할 컬럼 번호나 SaveName을 설정한다.
>
> Word 속성은 SheetCol 속성에 설정된 컬럼에서 찾을 글자로 "\*"을 이용하여 문자열을 like 비교할수 있다.

- **속성**

|          |                                                    |
|:--------:|:--------------------------------------------------:|
|   속성   |                       설 명                        |
| SheetCol | Sheet에서 내려지는 데이터 컬럼 Index 또는 SaveName |
|   Word   |  찾을 문자열, 찾을 글자 앞뒤로 "\*" 을 사용 가능   |

- **하위요소**

|            |                                         |
|:----------:|:---------------------------------------:|
|    속성    |                  설 명                  |
| < Range> | 패턴을 설정할 데이터의 기준을 설정한다. |

- **Example**

```
<?xml version="1.0" ?>
<Excel>
<DataPattern>
<Standard SheetCol="0" Word="소계*">
<Range Col1="1" Col2="End" RowHeight="25">
<CellFormat>
<Merge>False</Merge>
<Alignment Horizontal="Center" Vertical="Center"/>
<Interior BackColor="0,255,0" />
<Font Name="굴림" Size="12" Bold="True" Italic="True"/>
</CellFormat>
</Range>
</Standard>
</DataPattern>
</Excel>
```

- **제공 버전**

> **7.0.0.0**### 6.4.8.1.1 Range 요소(DataPattern 요소의 하위)

> 엑셀의 셀에 원하는 글자를 설정할때 셀 영역을 의미한다.
>
> 이 요소는 데이터 패턴을 설정할 엑셀의 영역을 설정하기 위한 요소이다. 이 요소의 속성 Col1, Col2는 엑셀의 컬럼번호를 의미하며 엑셀은 컬럼을 1부터 시작하므로 Sheet의 시작행과 동일하게 처리하면 안된다.
>
> Col1, Col2 인자의 행번호를 마지막 행번호 사용할 경우 "End"라는 글자로 설정할수 있다.
>
> RowHeight 속성은 영역의 행높이를 설정하는것으로 픽셀로 설정하고, 설정하지 않을 경우 기본적으로 ["PageSet 요소 > DefaultRowHeight 요소"](mk:@MSITStore:D:\SVN\제품배포\IB%20Sheet%20Pro\IBSheet(A)\doc\3.x.x.x\IBSheet3.2.0.2.chm::/xml/excel_pageset_element.html#DefaultRowHeight)에서 설정하는 기본 행 높이로 사용된다.

- **속성**

|            |                                        |
|:----------:|:--------------------------------------:|
|    속성    |                 설 명                  |
|    Col1    |  엑셀 영역의 시작 컬럼번호 또는 "End"  |
|    Col2    | 엑셀 영역의 마지막 컬럼번호 또는 "End" |
| RowHeights |      엑셀 영역의 행높이, 픽셀단위      |

- **하위요소**

|                 |                                                          |
|:---------------:|:--------------------------------------------------------:|
|      속성       |                          설 명                           |
| <CellFormat>  | 엑셀 영역의 머지, 정렬, 색상이나 글꼴 등을 설정하는 요소 |
| <BorderStyle> |           엑셀 영역에서 테두리를 설정하는 요소           |

> 요소의 상세설명은 Label > Range의 하단 요소 설명을 참조한다.

- **Example**

```
<?xml version="1.0" ?>
<Excel>
<DataPattern>
<Standard SheetCol="0" Word="소계*">
<Range Col1="1" Col2="End" RowHeight="25">
<CellFormat>
<Merge>False</Merge>
<Alignment Horizontal="Center" Vertical="Center"/>
<Interior BackColor="0,255,0" />
<Font Name="굴림" Size="12" Bold="True" Italic="True"/>
</CellFormat>
<BorderStyle>
<TopEdge Style="Dash" Weight="Medium" Color="255,0,0"/>
<BottomEdge Style="Dash" Weight="Medium" Color="0,0,0"/>
<LeftEdge Style="Continuous" Weight="Hairline" Color="0,0,255"/>
<RightEdge Style="Continuous" Weight="Hairline" Color="0,0,0"/>
</BorderStyle>
</Range>
</Standard>
</DataPattern>
</Excel>
```

- **제공 버전**

> **7.0.0.0**
>
> **  **