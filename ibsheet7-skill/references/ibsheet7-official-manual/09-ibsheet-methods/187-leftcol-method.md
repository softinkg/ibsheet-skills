# LeftCol Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > LeftCol Method

---

- **기능**

> 가장 좌측에 표시되는 컬럼을 확인하거나 설정한다. 틀고정 컬럼이 있을경우 고정 컬럼 이후 가장 좌측에 표시 된다. 이 속성의 설정으로 포커스는 변경되지 않지만 가장 좌측에 표시되는 컬럼이 바뀌므로 자동으로 수평 스크롤이 움직이게 된다. LeftCol은 Hidden 컬럼을 포함하여 0 컬럼을 기준으로 설정된다.

- **Syntax**

|        |     |                        |
|:------:|:---:|------------------------|
| Syntax | Get | ObjId.**GetLeftCol**() |

- **Info**

> **Return**: Long, 가장좌측 끝 컬럼 인덱스 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//컬럼으로 설정됨을 확인
mySheet.GetLeftCol();
```

- **Syntax**

|        |     |                           |
|:------:|:---:|---------------------------|
| Syntax | Set | ObjId.**SetLeftCol**(Col) |

- **Info**

> **Return**: None

| Parameter | Type         | 필수여부 | 설 명                            |
| --------- | ------------ | ---- | ------------------------------ |
| Col       | Long/ String | 필수   | 특정컬럼의 Column Index 또는 SaveName |

- **Example**

```
//고정컬럼이 설정되어 있을경우
//4컬럼을 수평스크롤 가장 좌측에 보이는 컬럼으로 설정
mySheet.SetLeftCol(4);
//고정컬럼이 설정되어 있지 않을경우
//6컬럼을 수평스크롤 가장 좌측에 보이는 컬럼으로 설정
mySheet.SetLeftCol(6);
```

- **제공 버전**

7.0.0.0