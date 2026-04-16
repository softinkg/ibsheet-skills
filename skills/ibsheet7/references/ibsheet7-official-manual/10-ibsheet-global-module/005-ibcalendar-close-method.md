# IBCalendar.Close Method

> **IBSheet7 개발자 가이드** > IBSheet Global Module > IBCalendar.Close Method

---

- **기능**

> 외부의 컨트롤에서 사용한 달력팝업을 닫도록 설정한다.

- **Syntax**

|        |                         |
|:------:|-------------------------|
| Syntax | **IBCalendar.Close**(); |

- **Info**

> **Return**: None

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
| 없음        |      |      |     |

```
// 달력 팝업을 띄운다.
IBCalendar.Show("20121116", {Format :"yyyy/MM/dd", X :300, Y :600}) ;
// 띄운 달력 팝업 Dialog를 닫는다.
IBCalendar. Close();
```

- **제공 버전**

7.0.0.0