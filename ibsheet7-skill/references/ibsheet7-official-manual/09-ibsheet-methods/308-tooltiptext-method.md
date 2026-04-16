# ToolTipText Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ToolTipText Method

---

- **기능**

> 셀의 풍선도움말을 설정하거나 확인한다.
>
> 헤더 행이든 데이터 행이든 셀 각각의 풍선도움말을 설정할거나 확인할 수 있고, 해당 셀에 마우스를 잠시 머무르고 있으면 풍선도움말이 표시된다.

- **Syntax**

|        |     |                                    |
|:------:|:---:|------------------------------------|
| Syntax | Get | ObjId.**GetToolTipText**(Row, Col) |

- **Info**

> **Return**: String, 현재 설정된 값 (Get Method 인 경우)

| Parameter | Type          | 필수여부 | 설 명                            |
| --------- | ------------- | ---- | ------------------------------ |
| Row       | Long          | 필수   | 해당 셀의 Row Index                |
| Col       | Long / String | 필수   | 해당 셀의 Column Index 또는 SaveName |

- **Example**

```
// 풍선 도움말 설정값을 확인
alert(mySheet.GetToolTipText(1, 1));
```

- **Syntax**

|        |     |                                             |
|:------:|:---:|---------------------------------------------|
| Syntax | Set | ObjId.**SetToolTipText**(Row, Col, ToolTip) |

- **Info**

> **Return**: None

| Parameter | Type          | 필수여부 | 설 명                            |
| --------- | ------------- | ---- | ------------------------------ |
| Row       | Long          | 필수   | 해당 셀의 Row Index                |
| Col       | Long / String | 필수   | 해당 셀의 Column Index 또는 SaveName |
| ToolTip   | String        | 필수   | 풍선 도움말 설정 값                    |

- **Example**

```
//셀에 풍선 도움말 설정
mySheet.SetToolTipText(1,1, "셀의 금액은 " + mySheet.GetCellText(1,1) + "입니다. ");
```

- **제공 버전**

> **7.0.0.0**