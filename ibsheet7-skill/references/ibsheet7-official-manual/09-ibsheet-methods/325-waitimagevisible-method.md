# WaitImageVisible Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > WaitImageVisible Method

---

- **기능**

> 각종 처리 중 대기 이미지의 표시여부를 설정하거나 확인한다.
>
> 조회,저장과 같은 EndUser의 대기 시간이 소요되는 함수를 호출하면 기본적으로 대기이미지를 표시한다.
>
> 이렇게 표시되는 대기 이미지를 어떤 이유로 사용하기 않고자 할 때 이 속성을 0으로 설정하여 대기 이미지를 더 이상 표시하지 않도록 한다.
>
> 이 속성의 설정에 따라서 모든 처리 중의 대기 이미지가 결정되어 표시되기도 하고, 표시 되지 않을수도 있다.

- **Syntax**

|        |     |                                 |
|:------:|:---:|---------------------------------|
| Syntax | Get | ObjId.**GetWaitImageVisible**() |

- **Info**

> **Return**: Boolean, 현재 설정 값(Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//처리 중 대기 이미지 표시 여부를 확인한다.
Alert(mySheet.GetWaitImageVisible());
```

- **Syntax**

|        |     |                                        |
|:------:|:---:|----------------------------------------|
| Syntax | Set | ObjId.**SetWaitImageVisible**(Visible) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명             |
| --------- | ------- | ---- | --------------- |
| Visible   | Boolean | 필수   | 각종 대기 이미지 표시 여부 |

- **Example**

```
//처리 중 대기 이미지를 표시하지 않도록 설정한다..
mySheet.SetWaitImageVisible(0);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **