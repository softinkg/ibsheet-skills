# EditEnterBehavior Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > EditEnterBehavior Method

---

- **기능**

> 데이터를 Edit 후 Enter 키를 눌렀을 때 동작을 확인하거나 설정한다
>
> 이 속성은 EnterBehavior Method와 구분하여 사용해야 한다. EnterBehavior Method 는 편집상태가 아닌 단순히 포커스가 있는 상태에서 Enter 키를 누른 경우이고, 이 속성은 편집상태에서 입력을 종료하기 위해
>
> Enter 키를 누른 상태로 구분하여 사용한다.

Newline 속성값 설정시 InitColumns에서 MultiLineText 속성이 1로 설정된 컬럼에 대하여 개행처리가 된다.

|         |                                         |
|:-------:|:---------------------------------------:|
|   값    |                  설명                   |
|   tab   |  편집 완료 후 오른쪽 셀로 포커스 이동   |
|  down   |  Down 키를 누른 것 처럼 아래셀로 이동   |
| newline |  줄바꿈되어 개행 처리 됨 (가능한 경우)  |
|  none   |    편집 완료 후 해당 셀 포커스 유지     |
| editTab | 편집 완료 후 다음 편집 가능한 셀로 이동 |

- **Syntax**

|        |     |                                  |
|:------:|:---:|----------------------------------|
| Syntax | Get | ObjId.**GetEditEnterBehavior**() |

- **Info**

> **Return**: String, 설정한 속성 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// Enter키의 동작을 확인한다.
mySheet.GetEditEnterBehavior( );
```

- **Syntax**

|        |     |                                      |
|:------:|:---:|--------------------------------------|
| Syntax | Set | ObjId.**SetEditEnterBehavior**(Mode) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                                          |
| --------- | ------ | ---- | -------------------------------------------- |
| Mode      | String | 필수   | 편집상태에서 Enter key 입력시 설정할 속성 값. Default="tab" |

- **Example**

```
// Edit 후 Enter를 누르면 무조건 아래로 이동하게 한다.
mySheet.SetEditEnterBehavior( "down");
```

- **제공 버전**

|  **7.0.0.0**  |                     |
|:-------------:|---------------------|
| **7.0.13.16** | "editTab" 모드 추가 |

> **  **