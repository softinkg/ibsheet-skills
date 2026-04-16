# WaitImage Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > WaitImage Method

---

- **기능**

> 처리 중 대기 이미지 파일의 위치를 설정하거나 확인한다.
>
> 이 속성은 기본적으로 제공하는 처리 중 대기 이미지를 사용자가 원하는 이미지로 변경설정 가능하기 위한 속성으로 조회 중 대기 이미지와 저장 중 대기 이미지를 모두 포함하고 있는 처리 중 대기 이미지이다.

- **Syntax**

|        |     |                          |
|:------:|:---:|--------------------------|
| Syntax | Get | ObjId.**GetWaitImage**() |

- **Info**

> **Return**: String, 현재 설정 되어 있는 URL (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//처리 중 대기 이미지 위치를 확인한다.
mySheet.GetWaitImage();
```

- **Syntax**

|        |     |                             |
|:------:|:---:|-----------------------------|
| Syntax | Set | ObjId.**SetWaitImage**(Url) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명     |
| --------- | ------ | ---- | ------- |
| Url       | String | 필수   | 이미지 Url |

- **Example**

```
//처리 중 대기 이미지를 변경한다.
mySheet.SetWaitImage("/sheet/imgWait.gif");
```

- **제공 버전**

> **7.0.0.0**