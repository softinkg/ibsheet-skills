# ScrollInfoPosition Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > ScrollInfoPosition Method

---

- **기능**

> 세로 스크롤 지연 처리 시간동안 표시되는 메시지의 출력 위치를 설정하거나 확인 한다. 설정 가능한 값은 아래와 같다.

| 예약어 | 설명                       |
|:------:|----------------------------|
|  none  | 표시 하지 않음             |
| center | 화면 중앙에 표시 (Default) |
| scroll | 스크롤 위치에 표시         |

- **Syntax**

|        |     |                                   |
|:------:|:---:|-----------------------------------|
| Syntax | Get | ObjId.**GetScrollInfoPosition**() |

- **Info**

> **Return**: String, 현재 설정값

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
//현재 설정되어있는 스크롤 정보 메시지 포맷을 확인 한다.
Console.log("ScrollInfoPosition :", mySheet.GetScrollInfoPosition());
```

- **Syntax**

|        |     |                                      |
|:------:|:---:|--------------------------------------|
| Syntax | Set | ObjId.**SetScrollInfoPosition**(Pos) |

- **Info**

> **Return**: None

| Parameter | Type   | 필수여부 | 설 명                        |
| --------- | ------ | ---- | -------------------------- |
| Pos       | String | 필수   | 메시지 출력 위치 (Default:center) |

- **Example**

```
// 메시지 출력을 스크롤 위치에 표시되도록 설정
mySheet.SetScrollInfoPosition("scroll");
```

- **제공 버전**

| **7.0.13.11** |     |
|---------------|-----|

> **  **