# Visible Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > Visible Method

---

- **기능**

> IBSheet의 표시 여부를 설정하거나 확인한다.
>
> 0으로 설정하면 건수 정보를 포함한 모든 것이 숨겨져서 보이지 않으며, 1로 설정하면 모든 정보를 볼수 있다.

- **Syntax**

|        |     |                        |
|:------:|:---:|------------------------|
| Syntax | Get | ObjId.**GetVisible**() |

- **Info**

> **Return**: Boolean, 현재 설정 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 시트 표시 여부를 확인
if(mySheet.GetVisible()){
alert("IBSheet를 표시함");
}else{
alert("숨겨져 있음");
}
```

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Set | ObjId.**SetVisible**(Visible) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명          |
| --------- | ------- | ---- | ------------ |
| Visible   | Boolean | 필수   | 화면에 시트 표시 여부 |

- **Example**

```
// 시트를 안보이게 설정
mySheet.SetVisible(0);
```

- **제공 버전**

> **7.0.0.0**