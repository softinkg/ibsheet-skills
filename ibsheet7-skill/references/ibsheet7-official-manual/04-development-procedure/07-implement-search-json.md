# 4.7 조회JSON 구현하기

> **IBSheet7 개발자 가이드** > 개발 절차 > 4.7 조회JSON 구현하기

---

> **javascript언어의 특성상 json 유형은 대소문자를 정확하게 지켜야 한다.**  
>   
> 조회 함수를 호출하면 인자로 넘긴 URL로 페이지에 연결한다. JSON 형태로 구성된 페이지의 내용을 읽어 들여 데이터로 표현한다.

- **조회된 내역이 있는 경우**

> 컬럼 초기화시 설정한 SaveName 으로 Key값을 설정한 경우 해당 SavName의 컬럼과 매핑되어 조회된다.
>
> [savename을 사용하는 예]

```
{
Etc:{"USER":"황상구","CRTDATE":"20130120"}

Message:"조회가 정상 처리되었습니다.",
Data: [
{SANO: 070712, SANM:'홍길동', CLSCD:'5',DEPTCD:'054'},
{ SANO: 020457, SANM:'김대한', CLSCD:'4',DEPTCD:'040'}
]
}
```