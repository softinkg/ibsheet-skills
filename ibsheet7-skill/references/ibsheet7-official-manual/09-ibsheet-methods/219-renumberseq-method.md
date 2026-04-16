# ReNumberSeq Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ReNumberSeq Method

---

- **기능**

> Seq 컬럼타입에 대한 데이터 순번을 재설정 한다.
>
> Order 인자의 설정에 따라 오름차순 또는 내림차순으로 설정 할 수 있으며 설정 값은 대소구분없이 처리 된다.

- **Syntax**

|        |                                |
|:------:|--------------------------------|
| Syntax | ObjId.**ReNumberSeq([Opt])** |

- **Info**

> **Return**: None

| Parameter      | Type    | 필수여부 | 설 명                                                                                                       |
| -------------- | ------- | ---- | --------------------------------------------------------------------------------------------------------- |
| Opt.Order      | String  | 선택   | 넘버링 처리 방식 (Default="asc") \| 설정값  \| 설명    \| \| ---- \| ----- \| \| asc  \| 오름 차순 \| \| desc \| 내림 차순 \| |
| Opt.VisibleRow | Boolean | 선택   | 숨김행 Seq 적용여부(Default="0")                                                                                 |

- **Example**

```
//컬럼의 Type이 Seq인 컬럼의 숫자를 1부터 다시 메긴다.
mySheet.ReNumberSeq();
// 역순 넘버링 처리
mySheet.ReNumberSeq("desc");
//Type:”Seq” 컬럼인 데이터를 숨겨진 컬럼을 제외하고 다시 처리
mySheet.ReNumberSeq({VisibleRow :1});
```

- **제공 버전**

| **7.0.0.0**  |                 |
|:------------:|-----------------|
| **7.0.13.5** | Order 인자 추가 |