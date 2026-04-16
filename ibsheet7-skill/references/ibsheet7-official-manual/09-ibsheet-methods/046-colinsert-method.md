# ColInsert Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ColInsert Method

---

- **기능**

> 특정 위치에 컬럼을 생성 한다.
>
> 생성위치(Pos)를 설정한 경우 해당 위치에 생성하고 설정하지 않은 경우 마지막 위치에 생성 한다.
>
> 컬럼타입이 Seq, Status, DelCheck인 컬럼은 생성이 불가능 하며 컬럼생성시 CalcLogic 속성은 사용이 불가능 하다.
>
> 생성할 컬럼의 설정 속성 집합 객체는 [InitColumns Method의 내용을 참조](#initcolumns-method) 한다. 컬럼의 설정 속성을 설정하지 않은 경우 "Text" 타입의 컬럼으로 생성 한다.

- **Syntax**

|        |                               |
|:------:|-------------------------------|
| Syntax | ObjId.**ColInsert**([Info]) |

- **Info**

> **Return**: None

| Parameter         | Type           | 필수여부 | 설 명                                                             |
| ----------------- | -------------- | ---- | --------------------------------------------------------------- |
| Info.Pos          | Number /String | 선택   | 생성할 위치의 컬럼 Index 또는 SaveName (Default : 마지막 컬럼)                 |
| Info.Header.Text  | String         | 선택   | 헤더에 설정할 문자열 (헤더가 2줄이상인 경우 구분자 "\|"로 연결한 문자열로 설정) (Default : "") |
| Info.Header.Align | String         | 선택   | 헤더 문자열의 정렬값 (Default : "Center")                                |
| Info.Col          | Object         | 선택   | 생성할 컬럼의 설정 속성 집합 객체                                             |

- **Example**

```javascript
// 마지막 위치에 기본("Text" 컬럼타입) 컬럼을 생성 한다.
var info = {
Header : {Text : "기본타입"}
};
mySheet.ColInsert(info);
// Index 3의 위치에 "CheckBox" 타입의 컬럼을 생성 한다.
var info = {
Pos:3,
Header:{Text: "체크박스",Align: "Left"},
Col:[{
Type: "CheckBox",
Width:60,
SaveName: "sCheckBox"
}]
};
mySheet.ColInsert(info);
```

- **제공 버전**

**7.0.0.0**

> **  **