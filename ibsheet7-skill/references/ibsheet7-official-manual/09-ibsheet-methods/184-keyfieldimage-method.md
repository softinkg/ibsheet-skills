# KeyFieldImage Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > KeyFieldImage Method

---

- **기능**

> 필수 입력 항목에 대한 이미지 파일의 위치를 설정하거나 확인한다.
>
> 이 속성은 기본적으로 제공하는 필수 입력 항목 이미지를 사용자가 원하는 이미지로 변경설정 가능하기 위한 속성이다.

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Get | ObjId.**GetKeyFieldImage**() |

- **Info**

> **Return**: String, 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 필수 입력 항목 이미지를 확인한다.
mySheet.GetKeyFieldImage();
```

- **Syntax**

|        |     |                                    |
|:------:|:---:|------------------------------------|
| Syntax | Set | ObjId.**SetKeyFieldImage**(imgUrl) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명     |
| --------- | ------ | ---- | ------- |
| imgUrl    | String | 필수   | 설정할 Url |

- **Example**

```
// 필수 입력 항목 이미지를 변경한다.
mySheet.SetKeyFieldImage("/sheet/imgKeyField.gif");
```

- **제공 버전**

7.0.0.0