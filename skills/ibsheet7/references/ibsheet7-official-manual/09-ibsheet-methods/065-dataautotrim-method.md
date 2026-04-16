# DataAutoTrim Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > DataAutoTrim Method

---

- **기능**

> 조회 또는 저장 시 데이터의 공백 트림 여부를 확인하거나 설정한다.
>
> 기본적으로 조회하거나 저장할 때 데이터 앞뒤에 있는 공백은 자동으로 트림되어 사용되지만 이 속성을 0로 설정한다면 조회시 데이터에 있는 공백을 그대로 사용하고, 저장 시도 공백을 그대로 사용한다. 이 속성 설정은 조회나 저장 뿐만 아니라 CellValue 와 같은 속성에 모두 적용된다. 기본으로 데이터의 공백 트림 속성은 설정되어있다.

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Get | ObjId.**GetDataAutoTrim**() |

- **Info**

> **Return**: Boolean, 데이터의 공백Trim 설정값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//자동 트림여부 설정 확인하기
mySheet.GetDataAutoTrim();
```

- **Syntax**

|        |     |                                 |
|:------:|:---:|---------------------------------|
| Syntax | Set | ObjId.**SetDataAutoTrim**(Trim) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                          |
| --------- | ------- | ---- | ---------------------------- |
| Trim      | Boolean | 필수   | 설정할 데이터의 공백Trim값 Default = 1 |

- **Example**

```javascript
//자동 트림하여 조회하기
mySheet.SetDataAutoTrim(1);
mySheet.DoSearch("list.jsp");
//트림하지 않고 데이터 그대로 저장하기
mySheet.SetDataAutoTrim(0);
mySheet.DoSave("save.jsp");
```

- **제공 버전**

> **7.0.0.0  **