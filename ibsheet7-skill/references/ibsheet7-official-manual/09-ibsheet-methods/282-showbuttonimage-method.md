# ShowButtonImage Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ShowButtonImage Method

---

- **기능**

> 팝업과 콤보의 버튼 이미지를 표시하는 종류를 확인하거나 설정한다
>
> 초기 로드 시 버튼 이미지 표시 종류를 설정한다
>
> 설정할 표시 종류는 다음과 같다.

|      |                                                      |
|:----:|:----------------------------------------------------:|
| 종류 |                         설명                         |
|  0   |    Focus가 있을 때만 콤보, 달력, 팝업 이미지 표시    |
|  1   |         Edit 가능할때 달력, 팝업 이미지 표시         |
|  2   |             항상 달력, 팝업 이미지 표시              |
|  3   | Edit 가능할때 콤보, 달력, 팝업 이미지 표시 (Default) |
|  4   |          항상 콤보, 달력, 팝업 이미지 표시           |

- **Syntax**

|        |     |                                |
|:------:|:---:|--------------------------------|
| Syntax | Get | ObjId.**GetShowButtonImage**() |

- **Info**

> **Return**: Integer, 현재 설정 값(Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 팝업과 콤보의 버튼 이미지를 표시하는 종류를 확인한다.
mySheet.GetShowButtonImage();
```

- **Syntax**

|        |     |                                    |
|:------:|:---:|------------------------------------|
| Syntax | Set | ObjId.**SetShowButtonImage**(type) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명               |
| --------- | ------- | ---- | ----------------- |
| type      | Integer | 필수   | 설정 값 (Default =3) |

- **Example**

```
// Focus가 있을경우만 콤보와, 팝업이미지 표시된다.
mySheet.SetShowButtonImage(0);

// Edit가 가능할 때 팝업이미지가 표시된다.
mySheet.SetShowButtonImage(1);

// 항상 팝업이미지가 표시 된다.
mySheet.SetShowButtonImage(2);

// Edit 가능할때 콤보와 팝업이미지가 표시된다.
mySheet.SetShowButtonImage(3);

// 항상 콤보와 팝업 이미지가 표시된다.
mySheet.SetShowButtonImage(4);

```

- **제공 버전**

> **7.0.0.0**
>
> **  **