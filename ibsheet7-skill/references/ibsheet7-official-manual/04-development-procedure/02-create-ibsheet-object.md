# 4.2 IBSheet객체를 생성

> **IBSheet7 개발자 가이드** > 개발 절차 > 4.2 IBSheet객체를 생성

---

> **body테그 안에서 함수 호출**
>
> js파일을 추가한 뒤에 IBSheet 객체를 화면에 추가한다.
>
> 추가하는 방법은 **ibsheetinfo.js** 에 있는 createIBSheet(sheetid,width,height,[lang])함수를 이용하여 추가하게 된다.

```javascript
<body>
```javascript
//IBSheet 객체 생성 ( 객체 id , 너비 , 높이 )
createIBSheet("mySheet", "750px", "400px");
```
</body>
```

> 다국어를 사용하는 경우 ibmsg 파일을 언어별로 생성한 후 createIBSheet 함수를 이용하여 설정이 가능 하다.

```javascript
// IBSheet 객체 생성
createIBSheet("mySheet", "750px", "400px", "en");
```

> 위와 같이 **"en"**을 인자로 넣는 경우 IBSheet에서 사용하는 메시지 및 포맷형태를ibmsg.en 파일의 내용으로 사용하게 된다.(인자가 없는 경우는 ibmsg 파일 사용)
>
> ※ 인자를 사용하는 경우 인자를 확장자로 하는 ibmsg 파일이 반드시 존재하여야 한다.
>
> **참고1. body테그 밖에서 생성함수 호출**

```javascript
<script language="javascript">
function LoadPage(){
//IBSheet 객체 생성( DIV 객체 , 객체ID , 너비 , 높이 )
createIBSheet2( document.getElementById("sheetObj"),
"mySheet", "750px", "400px");
}
</script>
<body onload="LoadPage()">
<div id="sheetObj"></div>
</body>
```

> **참고2. ibsheet.cfg, ibmsg 파일을 javascript 내에 변수로 사용하는 방법**
>
> ibsheet는 createIBSheet()함수를 통해 객체가 생성될 때 ajax 통신으로 통해 3가지 필요파일(ibsheet.css,ibmsg,ibsheet.cfg)을 불러옵니다.  
> 이중 ibsheet.cfg 나 ibmsg 와 같은 파일은 특이한 확장자를 갖고 있어 일부 서버에서는 별도 설정(mine/type)을 해주어야만 사용하실 수 있습니다.  
> 그런데 위 파일들은 json 구조를 갖고 있으므로 내용을 javascript 변수에 담아 사용하실 수도 있습니다.  
> 방법은 아래와 같습니다.

```javascript
//cfg 파일의 내용을 javascript 변수에 담음.
var _IBS_Config = {
"Cfg" : {
"Down2Excel_Url" : "../jsp/Down2Excel.jsp",
"LoadExcel_Url" : "../jsp/LoadExcel.jsp",
"DirectLoadExcel_Url" : "../jsp/DirectLoadExcel.jsp",
"Down2Text_Url" : "../jsp/Down2Text.jsp",
"LoadText_Url" : "../jsp/LoadText.jsp",
..... 중략 .....
}
};
//ibmsg 파일의 내용을 javascript 변수에 담음
var _IBS_Message = {
.... 중략 ....
};
//createIBSheet 함수에서 변수를 적용
function createIBSheet(sheetid, width, height, locale) {
var div_str = "";
if (!locale) locale = "";
Grids.Locale = locale;
//ibmsg, ibsheet.cfg 파일을 변수로 대체
Grids.Config = _IBS_Config;
Grids.Msg = _IBS_Message;
.... 중략 ....
}
```