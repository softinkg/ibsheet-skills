# GetFilterParam Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > GetFilterParam Method

---

- **기능**

> SearchMode:3 은, 디비에서 부분 데이터를 가져와 조회하는 것이므로 필터링 기능 사용이 불가능하다. 이 경우 필터링 행의 필터값과, 필터링 할려는 옵션값을 서버에 넘겨서 디비에서 조회시 사용하여, 필터링한 것과 같은 데이터를 구하여 시트에서 조회하기 위한 QueryString 문자열을 구해오는 함수이다. **AllFilter**가 0인 경우, 전체 컬럼을, 1인 경우 필터링이 되어 있는 컬럼들만 대상으로 한다. 단 필터 셀에 값이 들어있어도, 옵션값이 0(사용 안함)인 경우는 무시한다.
>
> QueryString은 한 컬럼당 SaveName=CellValue&SaveName_opt=OptionValue 형식으로 구성되며 컬럼의 연결자 역시 "&"를 사용한다.

- **Syntax**

|        |                                                        |
|:------:|--------------------------------------------------------|
| Syntax | ObjId.**GetFilterParam**([AllFilter], [UrlEncode]) |

- **Info**

> **Return**: String, 조회 조건 Query String

| Parameter | Type    | 필수여부 | 설 명                      |
| --------- | ------- | ---- | ------------------------ |
| AllFilter | Boolean | 선택   | 전체 필터링 여부, Default =0    |
| UrlEncode | Boolean | 선택   | UrlEncode 여부, Default= 1 |

- **Option**

| **0**  | 사용 안 함           | **1**  | 같다          |
|:------:|:---------------------|:------:|:--------------|
| **2**  | 같지 않다            | **3**  | 작은          |
| **4**  | 작거나 같은          | **5**  | 큰            |
| **6**  | 크거나 같은          | **7**  | 단어로 시작함 |
| **8**  | 단어로 시작하지 않음 | **9**  | 단어로 끝남   |
| **10** | 단어로 끝나지 않음   | **11** | 포함함        |
| **12** | 포함하지 않음        |        |               |

- **Example**

```javascript
//필터행 전체 컬럼을 Param 형식의 스트링으로 구해오기.
var FilterStr = mySheet.GetFilterParam(1);
//필터링 된 컬럼들만 Param 형식의 스트링으로 구해오기.
var FilterStr = mySheet.GetFilterParam(0);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **