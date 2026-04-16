# SetCellImageStyle Method

> **IBSheet7 개발자 가이드** > IBSheet Methods > SetCellImageStyle Method

---

- **기능**

> Image 속성을 사용하는 경우 해당 셀의 이미지에 대한 설정을 한다.
>
> 2개행 이상의 단위데이터행 구조에서 Col 인자에 Index를 설정할 경우 첫번째 행의 해당인덱스 셀에 대해서 처리를 하고 SaveName으로 설정할 경우 설정한 행의 단위데이터행 내 해당 SaveName 셀에 대해서 처리한다.
>
> 이 함수를 통해 설정이 가능한 속성은 다음과 같다.

| 속성      | 타입    | 설명               |
|-----------|---------|--------------------|
| Image     | Integer | 이미지의 경로      |
| ImgAlign  | String  | 이미지의 표시 위치 |
| ImgWidth  | Integer | 이미지의 너비      |
| ImgHeight | Integer | 이미지의 높이      |

- **Syntax**

|        |                                               |
|:------:|-----------------------------------------------|
| Syntax | ObjId.**SetCellImageStyle**(Row, Col, Style); |

- **Info**

> **Return**: None

| Parameter | Type        | 필수여부 | 설 명                      |
| --------- | ----------- | ---- | ------------------------ |
| Row       | Long        | 필수   | 대상 행의 Index              |
| Col       | Logn/String | 필수   | 대상 컬럼의 Index 또는 SaveName |
| Style     | Object      | 필수   | 셀의 이미지관련 속성 객체           |

- **Example**

```javascript
//3번째 행의 3번째 컬럼에 이미지를 왼쪽에 표시.
var style = {Image: "myImage.gif", ImgHeight:20, ImgAlign:"Left"};
mySheet.SetCellImageStyle(3, 3, style);
//3번째 행의 3번째 컬럼에 ImageList의 1번째 이미지를 오른쪽에 표시.
mySheet.SetImageList(0, "image0.gif");
mySheet.SetImageList(1. "image1.gif");
var style = {Image: 1, ImgAlign:"Right"};
mySheet.SetCellImageStyle(3, 3, style);
```

- **제공 버전**

> **7.0.0.0**
>
> **  **