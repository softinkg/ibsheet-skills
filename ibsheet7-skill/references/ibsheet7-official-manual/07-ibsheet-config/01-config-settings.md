# 7.1 Config 설정

> **IBSheet7 개발자 가이드** > IBSheet Config > 7.1 Config 설정

---

> 모든 IB Sheet 에 전역으로 설정 하고자 할 때 ibsheet.cfg 파일에 해당 속성을 정의 한다. 파일의 포맷은 xml, json 형태이다.
>
> 예를 들어 엑셀 다운로드 Url 을 설정 한다면 다음과 같이 ibsheet.cfg 파일에 설정한다.

```
<SHEET>
<Cfg Down2Excel_Url="../jsp/Down2Excel.jsp" />
</SHEET>
또는
{
"Cfg" : {
"Down2Excel_Url" : "../jsp/Down2Excel.jsp"
}
}
```

> 전역 설정 할 수 있는 속성은 다음과 같다.