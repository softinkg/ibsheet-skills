# ShowProcessDlg Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ShowProcessDlg Method

---

- **기능**

> 시트 중앙에 대기중 이미지를 표시 한다.
>
> 인자에 따라서 조회, 저장, 다운로드, 업로드의 대기 이미지를 표시 할 수 있으며 각각의 대기 이미지는 메소드에서 설정한 이미지를 사용한다.
>
> 표시된 이미지를 닫을 경우에는 HideProcessDlg Method 를 이용한다.
>
> 설정 인자에 따른 이미지 종류는 다음과 같다

| Type     | 이미지 종류          | Method (설정/확인) |
|----------|----------------------|--------------------|
| Search   | 조회 대기 이미지     | SearchingImage     |
| Save     | 저장 대기 이미지     | SavingImage        |
| Download | 다운로드 대기 이미지 | DownloadingImage   |
| Upload   | 업로드 대기 이미지   | UploadingImage     |

- **Syntax**

|        |                                |
|:------:|--------------------------------|
| Syntax | ObjId.**ShowProcessDlg**(Type) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                          |
| --------- | ------ | ---- | ---------------------------- |
| Type      | String | 선택   | 대기 이미지 종류 (Default:"Search") |

- **Example**

```
// 저장중 대기이미지를 표시 한다..
mySheet.ShowProcessDlg("Search");
```

- **제공 버전**

> **7.0.0.0**
>
> **  **