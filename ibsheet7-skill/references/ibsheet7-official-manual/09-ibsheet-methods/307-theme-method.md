# Theme Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > Theme Method

---

- **기능**

> IBSheet 의 테마 디자인을 확인 하거나 설정한다.
>
> 설정하기 위해서는 사전에 테마 디자인을 작업 하여야 한다. (세부 사항은 가이드문서 마지막 부분의 **Appendix** 3.Theme 만들기 참조)

- **Syntax**

|        |     |                      |
|:------:|:---:|----------------------|
| Syntax | Get | ObjId.**GetTheme**() |

- **Info**

> **Return**: String, 현재 테마의 Prefix 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```javascript
//현재 설정되어 있는 테마를 확인
var Prefix = mySheet.GetTheme();
```

- **Syntax**

|        |     |                                    |
|:------:|:---:|------------------------------------|
| Syntax | Set | ObjId.**SetTheme**(Prefix, Folder) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명          |
| --------- | ------ | ---- | ------------ |
| Prefix    | String | 필수   | 테마의 Prefix 값 |
| Folder    | String | 필수   | 테마의 폴더 명     |

- **Example**

```
//Gray 테마를 적용한다.
mySheet.SetTheme("GG", "Gray");
```

- **제공 버전**

7.0.0.0