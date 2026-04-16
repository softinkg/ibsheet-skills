# 4.1 웹 페이지에 JS 파일 링크 걸기

> **IBSheet7 개발자 가이드** > 개발 절차 > 4.1 웹 페이지에 JS 파일 링크 걸기

---

> IBSheet 제품을 사용하기 위해서 다음 js 파일을 import 한다.(ibsheet.css 파일은 ibsheet.js 파일에서 알아서 참조함으로 별도로 화면상에 링크를 넣을 필요는 없다)

```javascript
<!-- 라이선스 파일 -->
<script language="javascript" src="/Sheet/ibleaders.js"></script>
<!-- 제품 파일 -->
<script language="javascript" src="/Sheet/ibsheetinfo.js"></script>
<script language="javascript" src="/Sheet/ibsheet.js"></script>

<!-- client import/export 기능 파일 -->
<script language="javascript" src="/Sheet/ibexcel.js"></script>
```

> 위 파일의 자세한 용도와 기능은 3장 부분을 참고.