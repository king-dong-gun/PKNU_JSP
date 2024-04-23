## JSP 학습 1일차
### HTML 기초 학습 
#### HTML 문서 기본 구조
- `html`은 웹 페이지와 그 내용을 구조화 하기 위한 코드이다.
- 태그: 웹 페이지에 콘텐츠를 표시하기 위해 사용하는 언어이다.
  - 태그는 소문자로 작성한다.
  - 여는 태그와 닫는 태그를 정확하게 입력한다.
  - 태그의 콘텐츠로 태그를 포함시킬 수 있다.
  - 들여쓰기를 적절하게 사용하는 것이 좋다.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="utf-8">
  <title>여기에는 문서의 제목을 입력해주세요</title>
</head>
<body>
여기에 웹페이지에 표시할 콘텐츠(태그)를 입력해주세요
</body>
</html>
```

![helloHTML](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/c8c349e4-18de-4368-97b0-42b16b4c81d4)



- `<!DOCTYPE html>`: 문서 형식 선언, 필수 서문
- `<meta charset="UTF-8">`: 인코딩 방식 설정
- `<head>`: 파일에 대한 정보를 제공하는 부분으로 html 태그와 body 태그 사이에 생성
  - 웹 페이지의 제목을 설정하는 `title` 태그를 **필수적으로 포함**
- `<title>`: 문서의 제목을 입력하는 태그, 여기에 입력한 제목은 웹 브라우저의 탭 메뉴에 표시
  - 웹페이지를 방문하는 웹 이용자는 탭 메뉴에 표시되는 텍스트를 보고 웹페이지가 제공하는 콘텐츠에 대해 짐작할 수 있으므로 무척 중요한 정보
- `<body>`: `<body>` 태그 내부의 모든 것들은 웹 페이지 상에 표시
  - 하나의 HTML 문서에는 하나의 `<body>` 요소만 포함


#### HTML 제목과 문단
##### 제목
```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="utf-8">
  <title>제목 태그별 크기 비교</title>
</head>
<body>
<h1>숫자가 1일 때의 제목 텍스트</h1>
<h2>숫자가 2일 때의 제목 텍스트</h2>
<h3>숫자가 3일 때의 제목 텍스트</h3>
<h4>숫자가 4일 때의 제목 텍스트</h4>
<h5>숫자가 5일 때의 제목 텍스트</h5>
<h6>숫자가 6일 때의 제목 텍스트</h6>
</body>
</html>
```


![제목과문단](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/241c1c0c-dcdc-444b-8d70-de66e36a3884)

- 위의 사진처럼 h1이 가장 텍스트가 크고 h6이 가장 작다.

##### 문단


```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>여기에는 문서의 제목을 입력해주세요</title>
</head>
<body>
<!--인용구 표시하기-->
<p>p태그는 문단을 나타낼 때 사용하는 태그입니다.</p>
<p>하나의 문단에는 일정한 여백이 형성되면서 화면 상에서 구분하기가 용이합니다.</p>
<blockquote cite="https://github.com/"> 제 Git 입니다.</blockquote>
<!--주소 남기기-->
<!--target을 사용하면 새 페이지가 열리면서 주소로 들어가집니다-->
<p>출처: <a href="https://github.com/" target="black"> https://github.com/</a>
</p>
<!--수평선 표시하기-->
<p>지금까지 스포츠 뉴스였습니다.</p>
<hr>
<p>날씨 예보입니다. 오늘은 하루종일 흐리고 바람이 강할 예정입니다.</p>
<!--목록 항목 표시하기-->
<p>맨유 선수 명단</p>
<ul>
  <li>
    브루노 페르난데스
  </li>
  <li>
    메이슨 마운트
  </li>
</ul>
<!--페이지가 로드될때 경고창 표시-->
<script>
  alert("경고창이 표시됩니다!");
</script>
<!--문자열의 공백 나타내기-->
<h1>공백이 &nbsp;&nbsp;있는 &nbsp;&nbsp;&nbsp;&nbsp;글자</h1>
<!--CSS로 글자색상과 배경색 지정하기-->
<link rel="stylesheet" href="style.css">
<h2>예시 색상1</h2>
<h3>예시 색상2</h3>


</body>
</html>
```

```css
h2 {
    color: white;
    background: black;
}
h3 {
    color: yellow;
    background: red;
}
```

![경고창](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/086b4d62-63b3-4102-8031-bab8495fffe7)



![paragraph](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/536f6b40-bfcd-4b64-9071-60944721e024)



- `<p>`: p 태그는 하나의 문단에 일정한 여백이 형성되어 화면상 구분하기 용이하기 때문에 자주 사용
- `<blockquote>`: 인용구 표시
- `<a href = 홈페이지 주소>`: 주소 남기기
- `<hr>`: 수평선 표시
- `<ul>`: 목록의 시작
- `<li>`: 목록 항목
- `<script>`: 경고창 나타내기
  - `alert("text")`: 경고창에 경고 메세지 남기기
- `&nbsp`: 문자열의 공백 나타내기
- `<link rel="stylesheet" href="클래스명.css">`: CSS파일을 가져와 style 지정


