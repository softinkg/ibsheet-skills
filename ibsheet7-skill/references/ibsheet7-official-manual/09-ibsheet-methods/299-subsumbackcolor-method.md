# SubSumBackColor Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SubSumBackColor Method

---

- **기능**

> 소계 행의 배경 색상을 확인하거나 설정한다.

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Get | ObjId.**GetSubSumBackColor**() |

- **Info**

> **Return**: String, 현재 설정된 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//소계 행 배경색상을 확인한다.
mySheet.GetSubSumBackColor();
```

- **Syntax**

|        |     |                                            |
|:------:|:---:|--------------------------------------------|
| Syntax | Set | ObjId.**SetSubSumBackColor**(Color, Index) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                                                                |
| --------- | ------ | ---- | ------------------------------------------------------------------ |
| Color     | String | 필수   | 설정하고자 하는 WebColor 값                                                |
| Index     | Number | 선택   | 소계행이 여러개인 경우 원하는 n번째 소계행의 배경색상을 지정 (인자는 1부터 시작, 인자가 없으면 소계행 전체 적용) |

- **Example**

```
//소계 행 배경색상을 녹색으로 설정
mySheet.SetSubSumBackColor("#00FF00");
//3번째 소계행 배경색상을 녹색으로 설정
mySheet.SetSubSumBackColor("#00FF00", 3);
```

- **제공 버전**

| **7.0.0.0** |  |
|:--:|----|
| **7.0.13.144** | 소계행이 여러 개일 때 원하는 위치의 소계행의 색상을 지정해줄 수 있는 Index Parameter 추가. |

-