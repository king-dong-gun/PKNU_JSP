## JSP 학습 2일차

### HTML 기초 학습

#### HTML 태그 유형

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>제목입니당</title>
</head>
<body>
<!--가장 큰 제목을 나타내는 헤더 태그-->
<h1>가장 큰 제목입니당</h1>
<!--텍스트를 이탤릭체로 표시(기울여쓰기)-->
<h1><i>이탤릭체 입니당</i></h1>
<!--텍스트를 평소보다 작게 표시-->
<h1><small>평소보다 텍스트가 작습니당</small></h1>
<!--아래 첨자를 사용하여 텍스트를 표시-->
<h1>아래 첨자를 사용하여<sub>표시합니당</sub></h1>
<!--위 첨자를 사용하여 텍스트를 표시-->
<h1>첨자를<sup>사용해 표시합니당</sup></h1>
<!--텍스트에 밑줄을 그어 삽입된 텍스트 표시-->
<h1>
    <ins>밑줄로 표시합니당</ins>
</h1>
<!--텍스트에 취소선을 그어 삭제된 텍스트 표시-->
<h1>
    <del>취소선입니당</del>
</h1>
<!--네 번째 수준의 헤더 태그(작은 제목)-->
<!--텍스트를 굵게하여 강조 표시-->
<h4><strong>작은 제목</strong>텍스트가 굵습니당</h4>
<!--인라인 텍스트 표시-->
<p>
    블록 레벨 텍스트 안에
    <mark>인라인 레벨 텍스트 입니당</mark>
</p>
</body>
</html>
```

![태그종류](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/a7512947-2226-4ace-800c-c519fc0dee09)

- `<i>`: 텍스트를 이틸릭체로 표시
- `<small>`: 평소보다 텍스트를 작게 표시
- `<sub>`: 아래 첨자를 사용하여 텍스트를 표시
- `<sup>`: 위 첨자를 사용하여 텍스트를 표시
- `<ins>`: 텍스트에 밑줄을 그어 표시
- `<del>`: 텍스트에 취소선을 그어 표시
- `<strong>`: 텍스트를 굵게 하여 강조 표시
- `<mark>`: 인라인 텍스트를 표시

#### 표 만들기

- 표 요소는 구조상 행(row)과 열(column)로 이루어져 있고, 행과 열이 만나는 지점인 셀(cell)이 하나의 항목을 나타내는 역할을 맡음.

![표](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/97c39471-d097-48c8-8b13-c90b6de86012)

- `<table border="1">`: 표를 생성함
- `border="1"` 속성을 사용하여 표의 경계선을 1픽셀로 설정
- `<caption>`: 제목에 자막을 추가, 표에 길이에 맞춰 가운데 정렬
- `<table>` : 하나의 표를 나타내는 태그
- `<tr>` : 표 안에서 하나의 행을 나타내는 태그
- `<th>` : 행 안에서 제목에 해당하는 셀을 나타내는 태그
- `<td>` : 행 안에서 항목에 해당하는 셀을 나태는 태그
- `<thead>` : 표의 제목을 나타내는 영역
- `<tbody>` : 표의 본문을 나타내는 영역
- `<tfoot>` : 표의 요약 부분을 나타내는 영역
- `colspan`: 행을 합침 (가로병합)
- `rowspan`: 열을 합침 (세로병합)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>국가별 최고의 축구선수</title>
<body>
<table border="1">
    <caption>
        <strong>국가별 최고의 축구선수</strong>
        <br>
        레전드들
    </caption>
    <thead>
    <tr>
        <th>한국 선수</th>
        <th>포르투갈 선수</th>
        <th>아르헨티나 선수</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td>박지성</td>
        <td>크리스티아누 호날두</td>
        <td>리오넬 메시</td>
    </tr>
    </tbody>
    <tfoot>
    <tr>
        <td>아시아인 최초 챔스우승</td>
        <td>챔스 득점 1위</td>
        <td>올타임 NO1</td>
    </tr>
    </tfoot>
</table>
</body>
```

![테이블](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/18b94004-6989-4852-a1b6-94733855a8cc)

##### 예제문제 1번

- 아래 그림과 같이 html 작성

- ![문제](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/a93c461f-1cf8-44c6-ae55-f261290223ba)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>테이블 테스트</title>
</head>
<body>
<table border="1">
    <caption><strong>시간표</strong></caption>
    <thead>
    <tr>
        <th></th>
        <th>월</th>
        <th>화</th>
        <th>수</th>
        <th>목</th>
        <th>금</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td>1교시</td>
        <td>영어</td>
        <td>국어</td>
        <td>과학</td>
        <td>미술</td>
        <td>기술</td>
    </tr>
    <!--열 변경-->
    <tr>
        <td>2교시</td>
        <td>도덕</td>
        <td>체육</td>
        <td>영어</td>
        <td>수학</td>
        <td>사회</td>
    </tr>
    </tbody>
</table>
</body>
</html>

```

- 출력

![문제풀이](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/01a73085-dd9e-43b2-8158-2fc9aa28f30c)

##### 예제문제 2번


- 아래 그림과 같이 html 작성


![문제2](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/66023bb5-9e40-4861-bc64-f04e33bb6b35)



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Table Test 2</title>
</head>
<body>
<table border="1">
    <!-- 첫 번째 행은 날짜 헤더를 포함합니다 -->
    <tr>
        <th rowspan="2">지역</th>
        <th colspan="2">22일(월)</th>
        <th colspan="2">23일(화)</th>
    </tr>
    <!-- 두 번째 행은 시간대 헤더를 포함합니다 -->
    <tr>
        <th>오전</th>
        <th>오후</th>
        <th>오전</th>
        <th>오후</th>
    </tr>
    <!-- 서울 데이터 -->
    <tr>
        <th>서울</th>
        <td>맑음</td>
        <td>맑음</td>
        <td>맑음</td>
        <td>흐림</td>
    </tr>
    <!-- 부산 데이터 -->
    <tr>
        <th>부산</th>
        <td>흐림</td>
        <td>맑음</td>
        <td>흐림</td>
        <td>흐림</td>
    </tr>
</table>
</body>
</html>


```

- 출력


![문제2풀이](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/3d7f1ba5-f663-4748-a43f-c57b20867f52)



#### 이미지 태그
##### 이미지 표시하기

- `<img src = "image_URL">`: 이미지를 지정할 때는 src 속성에 이미지의 URL을 입력
- `<img src="../image_URL"> `: 이미지가 상위 폴더에 있을때
- `<img src="하위폴더명/penguin.png">` or `<img src="./하위폴더명/penguin.png">`: 이미지가 하위 폴더에 있을때
- `<img src="image_URL" alt="이미지를 대신해 내가 등장!">`: 대체 택스트 추가
  - 대체 텍스트: 이미지가 아직 로드되지 않았거나 이미지 로드에 실패한 경우 이미지를 대신해 표시될 텍스트


![대체텍스트](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/ebc35c42-29b7-4945-99aa-85e2deb6184f)

- `<img src="image_URL" width="250" height="100">`: 이미지 크기 설정 


#### 오디오와 비디오
##### 오디오
- `controls` : 오디오 파일의 컨트롤 패널을 표시
- `autoplay` : 오디오를 자동 재생
- `muted` : 오디오를 음소거로 처리
- `loop` : 반복 재생 기능을 추가


##### 비디오
- 비디오 또한 오디오 표시 방식과 유사, `<video>`태그로 표시
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>비디오</title>
</head>

<body>
<video width="600" controls="controls">
    <source src="../../video/에릭센오피셜.mp4" type="video/mp4"/>
</video>

</body>
</html>
```

![비디오](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/fea731ea-330c-4548-8a74-27230f8a62f1)

