## JSP 학습 3일차

### HTML 기초 학습

#### HTML 입력받기
> `<input>`: 웹 페이지 이용자로부터 입력을 받기 위해 사용하는 태그 중 가장 대표적인 태그

- `<input>`태그의 핵심 속성 **`type`**
1. `<text>`: 일반 텍스트를 받는 유형
2. `<password>`: 비밀번호를 받는 유형, 화면에 표시되지 않음
3. `<number>`: 숫자를 입력받는 유형 -> 최대값, 최소값을 지정
4. `<color>`: 텍스트 입력 대신 클릭을 통해 색상을 입력 받는 방식
5. `<button>`: 클릭 할 수 있는 버튼을 생성
6. `<radio>`: 한 문제 당 하나의 항목만을 선택
7. `<checkbox>`: 여러 항목을 함께 선택 
8. `<label>`: 태그와 입력 요소를 짝 지어주는 방식


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>제목입니당</title>
</head>
<body>
<!--일반 text를 받는 입력 코드-->
type = "text" >> <input type = "text" name = "input">

<!--아이디와 비밀번호를 받는 입력 코드-->
<br>
아이디는 type = "text"로 입력합니다 >> <input type="text" placeholder="아이디를 입력하세요">
<br>
비밀번호는 type = "password"로 입력합니다 >> <input type="password" placeholder="비밀번호를 입력하세요">
<br>


<!--숫자를 입력 받는 코드-->
숫자는 0~10까지 받아볼까요? >> <input type="number" min="0" max="10" step="1"> 완료!
<br>
<!--색상을 입력 받는 코드-->
색상은 type = "color"로 입력합니다 >> <input type="color">
<br>
<!--버튼을 입력 받는 코드-->
버튼은 type = "button" value = "push"로 입력합니다 >> <input type="button" value="PUSH">
<br>
<!--체크 박스를 입력 받는 코드-->
레디오 코드 입력1 <input type="radio" name="subject" > 선택지1
<br>
레디오 코드 입력2 <input type="radio" name="subject"> 선택지2
<br>
레디오 코드 입력3 <input type="radio" name="subject"> 선택지3
<br>
체크박스 코드 입력1 <input type="checkbox" name="food"> 선택지1
<br>
체크박스 코드 입력2 <input type="checkbox" name="food"> 선택지2
<br>
체크박스 코드 입력3 <input type="checkbox" name="food"> 선택지3


</body>
</html>
```


![input](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/54cfdc10-51f0-4463-af67-9df57c0bc76c)



#### HTML 입력 요소를 만드는 태그들
- `<select>`: 여러가지 항목중 원하는 항목을 선택하는 드롭다운 메뉴 제공

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>제목입니당</title>
</head>
<body>
<select>
  <option>브루노 페르난데스</option>
  <option>알레한드로 가르나초</option>
  <option>마커스 래시포드</option>
  <option>라파엘 바란</option>
</select>
</body>
</html>
```

![select](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/838d3d35-e034-4c8b-82a2-bd3ca8baa65c)




- `<textarea>`: `<input>` 태그를 사용하면 한 줄 입력만 받지만, `<textarea>`태그는 여러 줄을 입력 받을 수 있음
  - `cols` : 텍스트 영역의 가로 너비를 지정, 이때 수치는 문자의 개수를 기준
  -  `rows` : 텍스트 영역의 세로 너비를 지정, 기준은 cols와 동일하게 문자의 개수

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>제목입니당</title>
</head>
<body>
<!--입력을 주는 최대 행과 열 설정-->
<textarea cols = "10" rows="6"></textarea>

</body>
</html>
```



![textarea](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/0318d755-9609-4b8f-8215-412e37d6ffbf)


- 텍스트가 세로로 더 길어지면 세로 스크롤이 생김


- `<progress>`: 작업 진전도 표시 
  - `max`: 작업 완료를 위해 필요한 작업량 지정, 유효범위 0 < max < 1
  - `value`: 화면에 표시할 진척도, `max`의 값보다 작거나 같아야함

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>제목입니당</title>
</head>
<body>

<p>작업 진행 중... 60%...</p>
<progress value="60" max="100"></progress>

</body>
</html>
```


![progress](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/6155b345-692f-42b1-b3e7-722057ed01c4)



- `legend`: 입력값들을 묶어주는 함수

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>제목입니당</title>
</head>
<body>

<form action = "#" method = "get">
  <fieldset>
    <legend> 제목을 입력합니다 </legend>
    입력값1 <input type="text">
    입력값2 <input type="text">
    <input type="submit">
  </fieldset>
</form>

</body>
</html>
```


![legned](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/eb8e1480-eeee-429c-ac2f-a6b75d8b2068)


- `optgroup`: `select`바에서 `option` 요소들을 그룹화

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>제목입니당</title>
</head>
<body>
<select>
    <optgroup label="메뉴1">
        <option>선택지1</option>
        <option>선택지2</option>
        <option>선택지3</option>
    </optgroup>
    <optgroup label="메뉴2">
        <option>선택지4</option>
        <option>선택지5</option>
        <option>선택지6</option>
    </optgroup>
</select>

</body>
</html>
```

![optgroup](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/f821875d-6370-472d-8f21-f2fec4422b36)


