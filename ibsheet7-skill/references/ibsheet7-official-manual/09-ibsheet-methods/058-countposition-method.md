# CountPosition Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > CountPosition Method

---

- **기능**

> 건수 정보를 IBSheet의 특정 영역에 보이도록 설정한다.
>
> 건수 정보는 CountFormat 메소드에 설정된 건수정보가 표시된다. 기본적으로 현재 위치 정보와 최종 건수 정보를 표시하며 스크롤 바를 움직이거나 행이 추가되었을 때 변경되어 표시된다.
>
> 설정 값 별로 개수 정보 표시 영역 정보는 다음과 같다.

|          |               |          |          |          |          |
|:--------:|:-------------:|:--------:|:--------:|:--------:|:--------:|
|  설정값  |       0       |    1     |    2     |    3     |    4     |
| 표시위치 | 표시하지 않음 | 좌측상단 | 우측상단 | 좌측하단 | 우측하단 |

- **Syntax**

|        |     |                              |
|:------:|:---:|------------------------------|
| Syntax | Get | ObjId.**GetCountPosition**() |

- **Info**

> **Return**: Integer, 설정된 출력정보 위치 값 (Get Method 인 경우)

| Parameter | Type | 필수여부 | 설 명 |
| --------- | ---- | ---- | --- |
|           |      |      |     |

- **Example**

```
// 개수 정보가 표시되지 않고 있다면 개수 정보를 좌측 상단에 표시한다.
If(mySheet.GetCountPosition() == 0) {
mySheet.SetCountPosition(1);
}
```

- **Syntax**

|        |     |                                      |
|:------:|:---:|--------------------------------------|
| Syntax | Set | ObjId.**SetCountPosition**(Position) |

- **Info**

> **Return**: None

| Parameter | Type    | 필수여부 | 설 명           |
| --------- | ------- | ---- | ------------- |
| Position  | Integer | 필수   | 설정할 출력정보 위치 값 |

- **Example**

```
// 개수 정보가 표시되지 않고 있다면 개수 정보를 좌측 상단에 표시한다.
If(mySheet.GetCountPosition() == 0) {
mySheet.SetCountPosition(1);
}
```

- **제공 버전**

> **7.0.0.0**