## JSP 학습 4일차

### HTML 기초 학습

#### 입력 폼 만들기

- `<form>`: 입력한 요소들의 값을 서버로 전송해주는 태그
- `<action>`: 폼 요소에 입력된 값들을 전달받아 처리할 서버의 프로그램을 지정
- `<method>`: 사용자가 입력한 내용들을 서버로 전솔할 때의 방식 지정
    - `get`: 입력 후 전송한 값이 주소창에 표시
    - `post`: 입력 후 전송한 값이 주소창에 표시되지 않음, 길이 제한이 없음

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>입력 폼 만들기</title>
</head>
<body>
<form method="post" action="example_server.php">
    <label for="id">아이디</label>
    <input type="text" id="id">
    <br>
    <label for="pw">비밀번호</label>
    <input type="password" id="pw">
    <br>
    <input type="submit" value="로그인">
</form>

</body>
</html>
```

![form](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/2a667bd0-ffc6-4583-be61-ae84ca601a31)

#### <div>와 <span>

##### <div>

> `<div>`: 레이아웃을 나눌때 사용, 가상의 레이아웃을 설정하며 주로 CSS와 사용

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>relation 사용하기</title>
</head>
<body>
<div id="wrap">
    <div class="box1">
        <div class="n1"> 첫번째</div>
        <div class="n2"> 두번째</div>
    </div>
</div>
<div class="box2">
    <h1>제목입니다</h1>
    <u1>
        <li>항목1</li>
        <li>항목2</li>
        <li>항목3</li>
        <li>항목4</li>
    </u1>
</div>

</body>
</html>
```

![div](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/6b47efb2-ffff-46f3-9b80-cba2930b9c56)

- `"wrap"`의 자식은 `box1`, `box2`이다.
- `box1`의 자식은 `n1`, `n2`이고, 둘의 관계는 형제 관계이다.
- `class`는 중복이 가능하나 `id`는 중복이 불가하다.

##### <span>

> `display`속성이 `block`이 아닌 `inline` 형식

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>inline 사용하기</title>
</head>
<body>
<span style="background-color:red">span1</span>
<span style="background-color:blue">span2</span>
<span style="background-color:green">span3</span>
</body>
</html>
```

![span](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/ed90b06f-4073-4acf-bf9d-68edd1b01e37)

- `span`은 줄바꿈이 되지 않고 레이아웃을 바꿀수 있다.

#### 태그 성질에 따른 분류

1. 블록 요소 태그

> - `html`, `body`, `div`, `p`, `ul`, `ol`, `li`, `dl`, `dt`, `dd`...etc
> - 연속해서 작성하면 세로 배열
> - **기본 가로 공간의 크기가 부모 태그와 동일하게 인식**
> - 공간값이 적용

2. 인라인 요소 태그

> - `a`, `span`, `strong`, `i`, `em`...etc
> - 연속해서 작성하면 가로 배열
> - **기본 가로 공간의 크기가 안쪽에 포함된 내용만큼 인식(컨텐츠)**
> - 공간값이 적용 안됨

3. 인라인 블록 요소 태그

> - `img`, `input`, `buttom`...etc
> - 연속해서 작성하면 가로 배열
> - **기본 가로 공간의 크기가 안쪽에 포함된 내용만큼 인식**
> - 공간값이 적용

#### CSS selector

- 특정 요소들을 선택하여 스타일을 적용
    - 전체 선택자: HTML 내부의 모든 태그에 같은 CSS 속성 적용
  ```html
      <style> * {
        color: red;
        background: aquamarine;
    }
    </style>
  ```
    - 태그 선택자: HTML 요소를 직접 지정해 CSS 속성 적용
  ```html
      <style> h1 {
        color: red;
        background: aquamarine;
    }
  ```
    - ID 선택자: #을 사용하며, ID 값이 존재해야만 사용 가능
  ```html
    <!--CSS-->
       <style>
       #header {
            width: 800px;
            margin: 0;
            background: aquamarine;
        }
        #wrap {
            width: 1000px;
            height: 400px;
            float: left;
            background: aqua;
        }
      </style>
    
      <!--HTML-->
      <div id = "header">
      <h3>header</h3>
      </div>
      <div id = "wrap">
      <h3>aside</h3>
    ```
  - 클래스 생성자: 주어진 값을 class 속성값으로 가진 HTML 요소 선택, 태그 앞에 마침표 사용
  ```html
  <!--CSS-->
  <style>
      .class1 {
        color: red;
    }
  </style>
  ```
  
  > ID 선택자는 한번만 사용되지만, 클래스 선택자는 재사용이 가능하다. (하지만 스크립트에서는 문제가 됨)