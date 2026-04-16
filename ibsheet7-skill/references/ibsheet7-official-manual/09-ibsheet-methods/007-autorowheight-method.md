# AutoRowHeight Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > AutoRowHeight Method

---

- **기능**

> 데이터 행의 높이를 자동으로 조정할지 여부를 확인하거나 설정한다.
>
> 이 속성이 1이면, 행의 글자를 모두 표시할수 있도록 행의 높이를 자동으로 높이거나 줄인다. 행의 높이가 변경되는 경우는 다음과 같다.

1)  InitColumns에 컬럼속성을 MultiLineText:1로 설정하여 키보드로 편집도중 Shift+Enter 키를 눌러 줄바꿈된 글자를 설정하는 경우

2)  InitColumns에 컬럼속성을 Wrap:1로 설정하여 컬럼너비조정에 따라 글자가 자동으로 줄바꿈된 경우

3)  줄바꿈된 글자를 삭제하여 행의 높이가 줄어드는 경우

4)  SetCellText, SetCellValue 로 줄바꿈된 글자를 설정한 경우

5)  조회, 엑셀업로드로 줄바꿈된 글자를 로드하는 경우

> 이 속성이 0이면, 행의 높이는 SetDataRowHeight 속성으로 설정된 높이인 한줄 높이로 고정된다.

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Get | ObjId.**GetAutoRowHeight**() |

- **Info**

> **Return**: Boolean, 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 설정값 확인
mySheet.GetAutoRowHeight();
```

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Set | ObjId.**SetAutoRowHeight**(Flag) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                        |
| --------- | ------- | ---- | -------------------------- |
| Flag      | Boolean | 필수   | 데이터행의 높이 자동조정 여부 Default=1 |

- **Example**

```
// 높이를 자동으로 조정하지 않고, 한줄 높이로 고정한다.
mySheet.SetAutoRowHeight(0);
```

- **제공 버전**

7.0.0.0