# RenderSheet Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > RenderSheet Method

---

- **기능**

> 행 추가 또는 컬럼 숨김 기능을 동시에 여러 개 사용하는 경우 속도개선을 위해 랜더링을 마지막에 한꺼번에 처리 하기 위한 기능을 한다.
>
> **주의! 이 속성을 0(false)으로 사용 후 반드시 1(true)로 설정 하여야 한다. 그러지 않으면 Sheet의 모양이 그려지지 않아서 깨지는 현상이 있을 수 있다.**
>
> 아래와 같은 기능을 동시에 여러 개 수행할 때 사용하면 속도 개선을 할 수 가 있다.
>
> *※ Render 인자를 2로 설정하는 경우 시트 영역 전체에 대한 강제 랜더링 처리를 할 수 있다.*

| 메소드           | 설명              |
|------------------|-------------------|
| ColHidden        | 컬럼 숨김         |
| DataInsert       | 행 추가           |
| InitCellProperty | 셀의 속성 재 설정 |

- **Syntax**

|        |                               |
|:------:|-------------------------------|
| Syntax | ObjId.**RenderSheet**(Render) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명                |
| --------- | ------- | ---- | ------------------ |
| Render    | Boolean | 필수   | 렌더링 여부 (Default=1) |

- **Example**

```javascript
// 30개의 행추가를 RenderSheet를 이용하여 속도개선 처리
mySheet.RenderSheet(0);
for (var i = 0; i <30; i++) {
mySheet.DataInsert();
}
mySheet.RenderSheet(1);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **