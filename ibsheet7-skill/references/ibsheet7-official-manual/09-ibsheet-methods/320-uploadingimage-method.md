# UploadingImage Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > UploadingImage Method

---

- **기능**

> 파일 업로드 중 대기 이미지 파일의 위치를 설정하거나 확인한다.
>
> 이 속성은 기본적으로 제공하는 파일 업로드 중 대기 이미지를 사용자가 원하는 이미지로 변경설정 가능하기 위한 속성이다.

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Get | ObjId.**GetUploadingImage**() |

- **Info**

> **Return**: String, 현재 설정값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//현재 설정되어있는 업로드 중 대기 이미지 경로를 확인한다.
Alert(mySheet.GetUploadingImage());
```

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Set | ObjId.**SetUploadingImage**(Url) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명     |
| --------- | ------ | ---- | ------- |
| Url       | String | 필수   | 이미지 URL |

- **Example**

```
//업로드 중 대기 이미지를 변경한다.
mySheet.SetUploadingImage( "/sheet/imgUpload.gif");
```

- **제공 버전**

> **7.0.0.0**
>
> **  **