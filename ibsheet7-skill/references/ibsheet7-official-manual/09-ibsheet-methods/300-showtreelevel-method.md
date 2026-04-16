# ShowTreeLevel Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ShowTreeLevel Method

---

- **기능**

> 데이터가 트리 형태일 때 보여질 트리 레벨을 설정한다.
>
> Level은 다음과 같은 결과가 처리된다.

|       |                         |
|:-----:|-------------------------|
| Level | 설명                    |
|   0   | 모두 접기               |
|  -1   | 모두 펼치기, Default    |
| 그 외 | 해당 레벨 만큼만 펼치기 |

> ChildStatus는 보여질 트리 레벨 이하 레벨인 Child의 상태를 설정한다.
>
> ChildStatus는 다음과 같은 값을 설정할 수 있다.

|             |                                  |
|:-----------:|----------------------------------|
| ChildStatus | 설명                             |
|      0      | 이전 상태를 그대로 유지, Default |
|      1      | 모두 접음                        |
|      2      | 모두 펼침                        |

- **Syntax**

|        |                                                     |
|:------:|-----------------------------------------------------|
| Syntax | ObjId.**ShowTreeLevel**([Level], [ChildStatus]) |

- **Info**

> **Return**: None

| Parameter   | Type    | 필수여부 | 설 명                                     |
| ----------- | ------- | ---- | --------------------------------------- |
| Level       | Integer | 선택   | 보여질 트리 레벨 수준. Default=-1                |
| ChildStatus | Integer | 선택   | 보여질 트리 레벨 이하 레벨의 펼침 상태를 설정한다. Default=0 |

- **Example**

```
//모두 접기
mySheet.ShowTreeLevel(0, 1);
//모두 펼치기
mySheet.ShowTreeLevel(-1);
```

- **제공 버전**

> **7.0.0.0**