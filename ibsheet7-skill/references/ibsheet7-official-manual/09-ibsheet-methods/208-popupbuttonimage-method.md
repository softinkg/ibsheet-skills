# PopupButtonImage Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > PopupButtonImage Method

---

- **기능**

> 대상 셀의 팝업 버튼 이미지를 변경한다.
>
> Image 인자는 사용할 이미지의 Url 또는 이미지리스트에 설정한 이미지 인덱스를 사용할 수 있다.
>
> Image 인자를 상대경로 Url로 설정하는 경우 테마폴더를 기준으로 설정한다.
>
> 경우 Col인자에 인덱스를 설정하면 단위데이터 첫번째 행에 대해서 처리하고, SaveName을 설정하면 설정행을 기준으로한 단위데이터내의 SaveName 컬럼에 대해서 처리한다.

- **Syntax**

|        |                                             |
|:------:|---------------------------------------------|
| Syntax | ObjId.**PopupButtonImage**(Row, Col, Image) |

- **Info**

> **Return**: 설정불가능 셀인경우 -1 반환

| Parameter | Type        | 필수여부 | 설 명                       |
| --------- | ----------- | ---- | ------------------------- |
| Row       | Long        | 필수   | 설정할 셀의 행 인덱스              |
| Col       | Long/String | 필수   | 설정할 셀의 컬럼 인덱스 또는 SaveName |
| Image     | Long/String | 필수   | 설정할 이미지 Url 또는 이미지인덱스     |

- **Example**

```
// 셀의 팝업버튼 이미지를 변경
mySheet.PopupButtonImage(2, 10, "/image/ic_popup.gif");
// sPopup 컬럼의 팝업버튼 이미지를 이미지리스트에 설정한 이미지로 변경
mySheet. PopupButtonImage (4, "sPopup", 1);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **