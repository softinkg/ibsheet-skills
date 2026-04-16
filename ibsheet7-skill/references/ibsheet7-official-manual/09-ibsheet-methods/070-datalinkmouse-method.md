# DataLinkMouse Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DataLinkMouse Method

---

- **기능**

> 데이터 행의 페이지 링크 여부를 확인하거나 설정한다.
>
> 데이터 행에 Click 또는 DblClick 시 링크 페이지가 연결되어 있다면 Mouse Cursor가 손가락 모양으로 변경되어 링크가 연결되어 있음을 알리기 위해 사용한다.
>
> Link 인자에 1값을 설정할 경우 해당 컬럼에서 Mouse Cursor가 손가락 모양으로 변경된다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 모든행에 대해서 처리를 하고 SaveName으로 설정할 경우 해당 SaveName이 포함된 행에 대해서만 처리 한다.

- **Syntax**

|        |     |                                 |
|:------:|:---:|---------------------------------|
| Syntax | Get | ObjId.**GetDataLinkMouse**(Col) |

- **Info**

> **Return**: Boolean, 설정된 링크 값 (Get Method 인 경우)

| Parameter | Type            | 필수여부 | 설 명                      |
| --------- | --------------- | ---- | ------------------------ |
| Col       | Number / String | 필수   | 특정 컬럼의 Index 또는 SaveName |

- **Example**

```
//데이터행의 페이지 링크 여부 확인한다.
mySheet.GetDataLinkMouse(1);
```

- **Syntax**

|        |     |                                       |
|:------:|:---:|---------------------------------------|
| Syntax | Set | ObjId.**SetDataLinkMouse**(Col, Link) |

- **Info**

> **Return**: None

| Parameter | Type            | 필수여부 | 설 명                      |
| --------- | --------------- | ---- | ------------------------ |
| Col       | Number / String | 필수   | 특정 컬럼의 Index 또는 SaveName |
| Link      | Boolean         | 필수   | 링크여부 설정                  |

- **Example**

```
//1,2 컬럼에서만 가능하도록 설정한다.
mySheet.SetDataLinkMouse(1, 1);
mySheet.SetDataLinkMouse(2, 1);
```

- **제공 버전**

> **7.0.0.0  **