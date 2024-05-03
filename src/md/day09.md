## JSP 학습 9일차

### HTML 기초 학습

#### viewport
- `viewport`: 작은 화면의 모바일 단말기에 웹 페이지 모두를 표시하려고 하니 전체적인 페이지의 배율이 조정되기 때문에 `viewport`를 사용하여 조정한다.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
1. 속성
- `width`: 가로크기를 조정한다.
- `initial-scale`: 페이지가 처음 로딩될 때 줌 레벨을 조정한다.
- `minimum-scale`: 최소 배율값, 기본값은 0.25
- `maximum-scale`: 최대 배율값, 기본값은 1.6
- `user-scalable`: 사용자의 확대/축소 기능을 설정, 기본값은 yes

2. 정의된 속성 값
- `device-width` : 기기의 가로 넓이 픽셀 값 (웹페이지의 가로(width) 값은 기기가 사용하는 가로 넓이 값(device-width) 만큼 적용하여 사용하라는 의미)
- `device-height` : 기기의 세로 높이 픽셀 값


3. 주의사항

- content 보다 작은 viewport width/height를 설정하면 무시됩니다.
- viewport에서 initial-scale을 설정하지 않고 width/height를 설정하면 전체 화면이 표시됩니다.
- viewport에서 initial-scale도 width/height를 설정하지 않으면 width=980px/height=1091px 이 됩니다.
- 표시 영역과 contents의 크기가 일치하지 않을때 initial-scale을 설정하면 의도하지 않은 layout이 발생합니다.



#### media query
- `media`: css에서 어떤 스타일을 선택적으로 적용하고 싶을 때 사용한다.*(Java의 if문이라고 생각하면 된다.)*
  - 데스크탑, 노트북, 휴대폰 등등 선택적 시트를 제공한다.



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>media_print</title>
    <style>
        @media screen {
            body {
                background-color: palevioletred;
            }
        }
            @media print {
                body {
                    background-color: red;
                }
            }
    </style>
</head>
<body>
<h1>맨체스터 유나이티드</h1>
<p>영국 잉글랜드 그레이터맨체스터 주의 트래포드를 연고로 하는 프로축구 구단이다.
    뉴턴 히스 LYR F.C.(Newton Heath LYR F.C.)라는 이름으로 창설되었다.
    1902년 4월 26일 지금의 이름인 맨체스터 유나이티드 F.C.로 개칭 하였고, 1910년에는 홈 경기장을 맨체스터 시 동북쪽의 뱅크 스트리트에서 서남쪽의 올드 트래포드로 이전했다.</p>

</body>
</html>
```

- `print` 미디어 타입


![print](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/78c9d8ba-6013-479f-8e6b-644aa9da9b5e)



![print2](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/70f363d1-5cde-45b3-93a7-3f23dd6d5c63)



#### 외부 라이브러리 아이콘을 사용하여 css 만들기
- `JavaScript`를 조금 참조해 모달창, 드롭메뉴 생성


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <!-- Viewport 설정으로 반응형 디자인을 위한 기초 환경 설정 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no, maximum-scale=1">
    <!-- 외부 CSS 파일 연결 -->
    <link rel="stylesheet" href="headPj.css">
    <!-- Font Awesome 아이콘 라이브러리 연결 -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css">
    <title>Nav Bar</title>
</head>
<body>
<!-- 네비게이션 바 구조 -->
<nav class="navbar">
    <!-- 로고 부분 -->
    <div class="navbar_logo">
        <i class="fa-solid fa-person-digging"></i> <!-- 로고 아이콘 -->
        <a href="#">하이브</a> <!-- 로고 텍스트 -->
    </div>
</nav>
<!-- 네비게이션 메뉴 -->
<ul class="navbar_menu">
    <li><a href="#">Home</a></li>
    <!-- 각 드롭다운 메뉴 설정 -->
    <li class="dropdown">
        <a href="#" id="lessafimLink">르세라핌</a>
        <ul class="dropdown-content">
            <li><a href="#">맴버</a></li>
            <li><a href="#">엘범</a></li>
            <li><a href="#">화보</a></li>
        </ul>
    </li>
    <li class="dropdown">
        <a href="#" id="newjeansLink">뉴진스</a>
        <ul class="dropdown-content">
            <li><a href="#">맴버</a></li>
            <li><a href="#">엘범</a></li>
            <li><a href="#">화보</a></li>
        </ul>
    </li>
    <li class="dropdown">
        <a href="#" id="ilicLink">아일릿</a>
        <ul class="dropdown-content">
            <li><a href="#">맴버</a></li>
            <li><a href="#">엘범</a></li>
            <li><a href="#">화보</a></li>
        </ul>
    </li>
    <li class="dropdown">
        <a href="#" id="btsLink">방탄소년단</a>
        <ul class="dropdown-content">
            <li><a href="#">맴버</a></li>
            <li><a href="#">엘범</a></li>
            <li><a href="#">화보</a></li>
        </ul>
    </li>
</ul>
<!-- 소셜 미디어 아이콘 -->
<ul class="navbar_icons">
    <li><i class="fa-brands fa-instagram"></i></li>
    <li><i class="fa-brands fa-facebook"></i></li>
</ul>
<!-- 각 메시지 모달 -->
<div id="messageModal1" style="display:none; position: fixed; left: 50%; top: 50%; transform: translate(-50%, -50%); padding: 20px; background-color: white; border: 1px solid black;">
    <p>르세라핌 페이지에 오신 것을 환영합니다!</p>
    <button onclick="document.getElementById('messageModal1').style.display='none'">닫기</button>
</div>
<div id="messageModal2" style="display:none; position: fixed; left: 50%; top: 50%; transform: translate(-50%, -50%); padding: 20px; background-color: white; border: 1px solid black;">
    <p>뉴진스 페이지에 오신 것을 환영합니다!</p>
    <button onclick="document.getElementById('messageModal2').style.display='none'">닫기</button>
</div>
<div id="messageModal3" style="display:none; position: fixed; left: 50%; top: 50%; transform: translate(-50%, -50%); padding: 20px; background-color: white; border: 1px solid black;">
    <p>아일릿 페이지에 오신 것을 환영합니다!</p>
    <button onclick="document.getElementById('messageModal3').style.display='none'">닫기</button>
</div>
<div id="messageModal4" style="display:none; position: fixed; left: 50%; top: 50%; transform: translate(-50%, -50%); padding: 20px; background-color: white; border: 1px solid black;">
    <p>방탄소년단 페이지에 오신 것을 환영합니다!</p>
    <button onclick="document.getElementById('messageModal4').style.display='none'">닫기</button>
</div>
<!-- JavaScript 이벤트 핸들러: 클릭 시 메시지 모달 표시 -->
<script>
    document.getElementById('lessafimLink').addEventListener('click', function (event) {
        event.preventDefault();
        document.getElementById('messageModal1').style.display = 'block';
    });
    document.getElementById('newjeansLink').addEventListener('click', function (event) {
        event.preventDefault();
        document.getElementById('messageModal2').style.display = 'block';
    });
    document.getElementById('ilicLink').addEventListener('click', function (event) {
        event.preventDefault();
        document.getElementById('messageModal3').style.display = 'block';
    });
    document.getElementById('btsLink').addEventListener('click', function (event) {
        event.preventDefault();
        document.getElementById('messageModal4').style.display = 'block';
    });
</script>
</body>
</html>

```


```css
/* 전체 페이지의 마진을 제거하여 여백 없이 시작 */
body {
    margin: 0;
}

/* 모든 링크의 기본 밑줄 스타일을 제거하고, 색상을 진한 파란색으로 설정 */
a {
    text-decoration: none;
    color: darkblue;
}

/* 네비게이션 바 설정: 가로 레이아웃, 요소 간 간격 동등 배분, 세로 중앙 정렬 */
.navbar {
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    align-items: flex-start;
    background-color: lavenderblush;
}

/* 네비게이션 바의 로고 스타일: 폰트 크기 및 색상 설정 */
.navbar_logo {
    font-size: 24px;
    color: rgb(234, 93, 93);
}

/* 네비게이션 메뉴의 스타일: 수평 방향으로 항목 정렬, 리스트 스타일 없음, 왼쪽 패딩 제거 */
.navbar_menu {
    display: flex;
    list-style: none;
    padding-left: 0;
}

/* 네비게이션 메뉴 항목에 대한 스타일: 인라인 블록으로 표시, 각 항목의 너비를 100%로 설정 */
.navbar_menu li {
    position: relative;
    display: inline-block;
    width: 100%;
}

/* 드롭다운 메뉴의 내용을 기본적으로 숨기고, 위치와 스타일을 지정 */
.dropdown-content {
    display: none;
    position: absolute;
    background-color: #f9f9f9;
    min-width: 160px;
    box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
    z-index: 1;
}

/* 드롭다운 내부 링크의 스타일: 색상, 패딩, 텍스트 정렬 */
.dropdown-content a {
    color: black;
    padding: 12px 16px;
    text-decoration: none;
    display: block;
    text-align: left;
}

/* 드롭다운이 호버될 때 내용을 표시 */
.dropdown:hover .dropdown-content {
    display: block;
}

/* 드롭다운 내부 링크가 호버될 때 배경 색상 변경 */
.dropdown-content a:hover {
    background-color: #ddd;
}

/* 네비게이션 바 아이콘 스타일: 리스트 스타일 없음, 색상 설정 */
.navbar_icons {
    list-style: none;
    color: blue;
}

/* 네비게이션 메뉴 항목이 호버될 때 배경 색상 변경 */
.navbar_menu li:hover {
    background-color: darkgray;
}

/* 화면 크기가 767px 이하일 때 네비게이션 바와 메뉴 스타일 변경: 세로 방향, 중앙 정렬 */
@media screen and (max-width: 767px) {
    .navbar {
        flex-direction: column;
        align-items: flex-start;
    }
    .navbar_menu {
        flex-direction: column;
        align-items: center;
        width: 100%;
    }
    .navbar_menu li {
        width: 100%;
    }
}

button {
    background-color: #4CAF50; /* 녹색 배경 */
    color: white; /* 흰색 텍스트 */
    padding: 10px 20px; /* 패딩 */
    border: none; /* 테두리 없음 */
    border-radius: 5px; /* 모서리 둥글게 */
    cursor: pointer; /* 마우스 포인터를 손가락 모양으로 변경 */
}

button:hover {
    background-color: #45a049; /* 호버 시 더 어두운 녹색으로 변경 */
}

```

- **웹페이지**

![하이브](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/a7f79523-4199-41b3-b371-a8076b8262ec)

- **모달창**

![모달창](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/6354cb85-d8df-4a16-9f9d-ad76ecb516f4)

- **drop 메뉴**

![르세라핌](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/f27f2da0-984a-4e60-9706-49c7011e9997)

