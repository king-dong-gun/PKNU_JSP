## JSP 학습 6일차

### HTML 기초 학습

#### CSS 선택자

##### 자식 선택자

- 요소 내부에 있는 해당 요소를 가리키지만 하위요소의 하위요소는 가리키지 않습니다.
- CSS 에서는 선택자 사이를  ">" 로 분리 합니다.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title></title>
    <style>
        /*
        <li>태그 : 자식 > <a>태그
        */
        li:nth-child(3) > a {
            color: red;
        }
    </style>
</head>
<body>
<ul>
    <li><a href="#">주의사항</a></li>
    <li><a href="#">주의사항</a></li>
    <li><a href="#">주의사항</a></li>
    <li><a href="#">주의사항</a></li>
    <li><a href="#">주의사항</a></li>
</ul>

</body>
</html>

<!--
<li> 태그의 자식 <a> 태그
<li> 태그의 첫번째 자식 <a> 태그 자식
-->

```

![자식선택자](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/74ead378-8397-49a6-9c78-07f24d63a0e9)


- `first-child`: 첫번째 자식을 선택
- `nth-child(n)`: n번째 자식을 선택
- `last-child`: 마지막 자식을 선택

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title></title>
    <style>
        p:nth-child(1), p:nth-child(2) {
            font-size: 100%;  /* 기본 크기와 같은 크기로 설정 */
        }
        p:nth-child(3) {
            font-size: 150%;  /* 기본 크기보다 50% 큰 크기로 설정 */
        }
        p:nth-child(4) {
            font-size: 200%;  /* 기본 크기의 두 배 크기로 설정 */
        }
    </style>
</head>
<body>
<p>맨체스터는 빨간색입니다.</p>
<p>맨체스터는 빨간색입니다.</p>
<p>맨체스터는 빨간색입니다.</p>
<p>맨체스터는 빨간색입니다.</p>
</body>
</html>

```

![글꼴스타일](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/2dc1760f-1bb7-409a-b844-4558fb1a9b94)



- 픽셀: 기본 글꼴이 16px, 150%면 24px, 200% 32px가 설정된다.
- em: 배수, 16px이면 1.0em, 24px면 1.5em, 32px면 2.0em 이다.


#### CSS 우선 적용 순위

1. !important 규칙
```html
color: red !important;
```
- `!important` 키워드를 붙히면 다른 규칙보다 우선순위로 적용된다.

2. 인라인 스타일
```html
<div style="color: blue;">이 텍스트는 파란색입니다.</div>
```
- HTML 요소에 직접 선언된 스타일(인라인 스타일)은 외부 또는 내부 스타일 시트에 선언된 스타일보다 더 높은 우선순위를 가진다. 인라인 스타일은 해당 HTML 요소에만 적용된다.

3. id 선택자
```html
#specific-id { color: green; }
```
- 한 HTML 문서 내에서 ID는 유일하므로, ID로 지정된 스타일은 매우 구체적이고 클래스 선택자나 태그 선택자보다 높은 우선순위를 가진다.

4. 클래스, 속성 선택자
```html
.my-class { color: orange; }
```
- 여러 요소에 동일한 스타일을 적용하는데 사용된다. 
- 여러 클래스가 동일 요소에 적용되면, 나중에 선언한 규칙이 우선 적용된다.

5. 태그 선택자
```html
p { color: black; }
```
- 요소의 기본 스타일을 정의하는 데 사용된다.
- 우선순위가 낮지만 HTML 문서 전체에 걸쳐 일관된 스타일을 제공한다.

6. 상속된 속성
- 특정 속성은 부모 요소에서 자식 요소로 상속될 수 있다.
  - `color`
  - `font`
  - `line-height`

#### 시각적 요소
- `margin`: 속성의 여백을 정의
  - 적용형태: 순서대로 상 우 하 좌를 정의
```html
margin: 10px 20px 30px 40px;
```

- `padding`: 속성의 내부 여백을 정의
  - 적용형태: 순서대로 상 우 하 좌를 정의
```html
padding: 10px 20px 30px 40px;
```

- `border`: 테두리를 정의
  - `thick`: 두꺼운 테두리
  - `dashed`: 긴 점선 테두리
  - `solid`: 실선 테두리
  - `dotted`: 점선 테두리
- `border-radius`: 테두리 곡선을 정의
  - 적용형태: 순서대로 좌상 우상 우하 좌하를 정의
```html
<style>
  .box {
    width: 150px;
    height: 80px;
    background-color: red;
    border: 2px;
  }
  #box1 {
    border-radius: 20px;
  }
  /*원을 만들때 높이와 크기의 속성을 맞춰주고 radius 50을 주면 원 완성!!*/
  #box2 {
    width: 80px;
    border-radius: 50px;
  }
  #box3 {
    border-radius: 20px 0 10px 50px;
  }
</style>
```


![border](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/a089a4e8-3e64-443b-9707-1d0e49b6f83f)


- `display`: *none*을 사용하면 화면에 보이지 않고, 공간도 차지하지 않는다.
```html

<style>
  #box {
    display: none;
  }
</style>
```
![display](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/5ffdf1c8-8326-4c6f-9570-bfeacd6a395a)


- `visibility`: *hidden*은 화면에는 보이지 않고, 공간은 차지한다.

```html
<style>
  #box {
    visibility: hidden;
  }
</style>
```

![visibility](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/dab83d68-03d5-4f9c-b56c-2183459041a8)


- `inline-block`: 인라인 속성의 블럭을 생성한다.

```html
    <style>

        #box {
            display: inline-block;
            background-color: red;
            width: 200px;
            height: 50px;
        }
```

![inline-block](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/2e2a57f2-c659-4e19-ba03-8f94ff304a96)
