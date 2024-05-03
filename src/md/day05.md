## JSP 학습 5일차

### HTML 기초 학습

#### CSS 선택자

- 선택자란 CSS로 UI의 어느 부분을 디자인할지 표현할 대상이 되는 부분이다.



##### 반응 선택자
- 사용자가 마우스를 갖다 대거나, 클릭 같은 반응을 하였을 때 스타일을 지정하는 사용자이다.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Selector Action</title>
    <style>
        h1:hover {
            color: red;
        }

        a:visited {
            color: green;
            font-size: 40px;
        }

        h3:active {
            color: blue;
        }
    </style>
</head>
<body>
<h1>hover : 마우스를 올렸을 때</h1>
<h2><a href="https://naver.com" target="_blank">네이버 방문하기</a></h2>
<h3>active : 클릭했을 때</h3>
</body>
</html>
```

![반응선택자](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/5ca1862b-fef7-4eb0-828d-cb11f98b575f)


##### 구조 선택자
- 특정 위치에 있는 태그들에게 스타일을 지정하는 선택자이다
  - `first-child`: 첫번째 태그
  - `last-child`: 마지막 태그
  - `nth-child(n)`: 여러 태그들에게 순번을 지정해준다.


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>구조 선택자</title>
  
    <style>
        li {
            list-style: none;
            float: left;
            padding: 15px;
        }
        li:nth-child(2n - 1) {background-color: aquamarine}
        li:nth-child(2n) {background-color: #5c7cfa}
        li:first-child{border-radius: 10px 0 0 10px}
        li:last-child{border-radius: 0 10px 10px 0}
    </style>

</head>
<body>
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
    <li>6</li>
    <li>7</li>
</ul>

</body>
</html>

```
![구조선택자](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/b3d6ae11-51a2-49d8-90da-f8155151cbe0)



##### 상태 선택자

- `<input>`태그를 받아 입력을 받는 상태에 스타일을 줄 때 사용한다.

  - `input : checked` -> check 상태인 input 태그를 선택
  - `input : focus` -> focus가 input된 태그를 선택
  - `input : enabled` -> 입력이 가능한 input 태그를 선택
  - `input : disabled` -> 입력이 불가능한 input 태그를 선택

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>CSS 상태 선택자</title>
    <style>
        input:focus {
            border: 2px solid red;
        }

        input:enabled {
            color: green
        }

        input:disabled {
            color: red
        }
    </style>
</head>
<form>
    <h2>사용가능</h2>
    아이디 : <input type="text" name="uid"/> <br/>
    비밀번호 : <input type="password" name="pwd"/> <br/>
    <h2>사용 불가능</h2>
    닉네임 : <input type="text" name="uname" value="사용불가능" disabled="disabled"/> <br/>
</form>
</body>
</html>

```


![상태선택자](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/6adb072f-67e8-404f-835b-0c65380e447f)
