# 6.3 Tree기능 사용시 JSON

> **IBSheet7 개발자 가이드** > 데이터 구조 > 6.3 Tree기능 사용시 JSON

---

> 특정 컬럼을 Tree 형태로 사용시 데이터 JSON의 기본 구조는 다음과 같다.

- **Example**

```
{data:[
{sa_nm:"김사장",job:" PRESIDENT",Items:[ //0 LEVEL
{sa_nm:"안전무",job:"GMANAGER"}, //1 LEVEL
{sa_nm:"이상무",job:"GMANAGER",Items:[ //1LEVEL
{sa_nm:"박대리",job:"ASSISTANT"} //2LEVEL
]}
]}
]}
```

> 단 위와 같은 json 구조를 구성하기 어려울 경우, xml와 같이 Level 프로퍼티를 이용한 방법도 기능으로 제공하고 있다.
>
> Level 인자를 이용한 방법
>
> 먼저 ibsheet.cfg 파일에 UseJsonTreeLevel = "1"로 설정

- **Example**

```
{data:[
{sa_nm:"김사장",job:" PRESIDENT",Level:0}, //0 LEVEL
{sa_nm:"안전무",job:"GMANAGER",Level:1}, //1 LEVEL
{sa_nm:"이상무",job:"GMANAGER",Level:1}, //1LEVEL
{sa_nm:"박대리",job:"ASSISTANT",Level:2} //2LEVEL
]}
```

- **제공 버전**

> **7.0.0.0**