# IBCalendar.SetTheme Method

> **IBSheet7 개발자 가이드** > IBSheet Global Module > IBCalendar.SetTheme Method

---

- **기능**

> 외부 컨트롤에서 사용할 달력팝업의 테마 디자인을 설정한다.
>
> 설정하기 위해서는 사전에 테마 디자인을 작업 하여야 한다.
>
> (세부 사항은 가이드문서 마지막 부분의 **Appendix** 3.Theme 만들기 참조)

- **Syntax**

|        |                                          |
|:------:|------------------------------------------|
| Syntax | **IBCalendar.SetTheme**(Prefix, Folder); |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명          |
| --------- | ------ | ---- | ------------ |
| Prefix    | String | 필수   | 테마의 Prefix 값 |
| Folder    | String | 필수   | 테마의 폴더 명     |

- **Example**

```
//Orange 테마를 적용한다.
IBCalendar.SetTheme("OR", "Orange");
```

- **제공 버전**

7.0.0.0