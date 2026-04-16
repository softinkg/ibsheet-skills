# ImageList Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ImageList Method

---

- **기능**

> N번째 이미지 파일의 웹서버 경로를 확인하거나 설정한다.
>
> Type이 Image인 셀에 표시하는 이미지의 경로를 미리 설정하여 1회 다운 받아 재사용하기 위해 이미지 파일을 기억을 기억하기 위한 속성이다 .
>
> 조회 및 신규행입력시 사용된다.
>
> 이미지 파일의 경로는 현재 페이지를 기준으로 상대경로를 사용하거나 웹서버 루트 이하의 절대경로를 설정하도록 한다.
>
> 인덱스로 설정할 경우 0부터 시작하며 원하는 개수만큼 설정하도록한다.
>
> [설정하는 방법]
>
> mySheet.SetImageList(0, "../image/btn_search.gif");
>
> mySheet.SetImageList(1,"/common/image/btn_cal.gif");
>
> [ 이미지관련 값변경시 사용하는 함수 정리 ]

| 이미지설정     | 상황    | Image                                                                                     |
| --------- | ----- | ----------------------------------------------------------------------------------------- |
| ImageList | 이미지변경 | SetCellValue,SetCellImage SetSearchingImage,SetSavingImage, SetWaitImage,SetKeyFieldImage |
| ImageList | 값변경   | 해당없음                                                                                      |

- **Syntax**

|        |     |                               |
|:------:|:---:|-------------------------------|
| Syntax | Get | ObjId.**GetImageList**(Index) |

- **Info**

> **Return**: String, 해당 인덱스에 설정한 Image경로 (Get Method 인 경우)

| Parameter | Type    | 필수여부 | 설 명       |
| --------- | ------- | ---- | --------- |
| Index     | Integer | 필수   | Image 인덱스 |

- **Example**

```
// 해당 인덱스에 설정한 이미지경로 확인
mySheet.GetImageList(0);
```

- **Syntax**

|        |     |                                    |
|:------:|:---:|------------------------------------|
| Syntax | Set | ObjId.**SetImageList**(Index, Url) |

- **Info**

> **Return**: None (Get Method 인 경우)

| Parameter | Type    | 필수여부 | 설 명          |
| --------- | ------- | ---- | ------------ |
| Index     | Integer | 필수   | Image 인덱스    |
| Url       | String  | 필수   | 설정할 Image 경로 |

- **Example**

```
// 0 인덱스에 이미지경로 설정
mySheet.SetImageList(0, "../image/btn_search.gif");
// 0 인덱스에 저장된 이미지 사용(Type:Image)
mySheet.SetCellValue(3, 5, 0);
mySheet.SetCellImage(3, 5, 0);
mySheet.SetSearchingImage(0);
mySheet.SetSavingImage(0);
mySheet.SetWaitImage(0);
mySheet.SetKeyFieldImage(0);
```

- **제공 버전**

7.0.0.0