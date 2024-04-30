## JSP 학습 7일차

### HTML 기초 학습

#### 폰트

##### 폰트 사이즈

1. 인라인 스타일을 사용하기
    - HTML 요소에 직접 style 속성을 사용하여 폰트 크기를 설정할 수 있다.

```html
<p style="font-size: 16px;">이 텍스트는 16픽셀 크기로 표시됩니다.</p>
```

2. CSS 사용하기
   - 외부 CSS 파일이나 `<style>` 태그를 사용하여 폰트 사이즈를 설정할 수 있다.
   - 이 방법은 웹페이지 전체에 걸쳐 일관된 스타일을 적용하는데 유용하다.

```html

<style>
    p {
        font-size: 20px;
    }
</style>
```

3. 상대 크기 단위 사용하기
    - `em`, `rem`, `%`와 같은 상대 크기 단위를 사용하여 폰트 사이즈를 설정할 수 있다.
    - 이러한 단위는 상위 요소의 폰트 사이즈에 따라 결정되기 때문에 유동적인 디자인에 적합하다.

```html

<style>
    <p style  =  "font-size: 1.5em;"  > 이 텍스트는 상위 요소의 폰트 크기에 따라  1.5  배 크기로 조정됩니다.
    </p>
</style>
```

##### 폰트 글꼴

- `font-family`: 폰트의 글꼴을 설정한다.

```html

<style>
    .font_arial {
        font-family: Arial;
    }

    .font_roman {
        font-family: "Times New Roman";
    }
</style>
```

![font-family](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/354d026f-aa42-4708-b2aa-d5a8d3f010fc)

- 두 단어 이상은 **""**를 사용하고, 한 단어일 때는 사용 안해도 괜찮다!

```html

<style>
    .h1 {
        font-family: "없는폰트", "Myanmar MN";
    }

    .p1 {
        font-family: "모르는 폰트", monospace;
    }
</style>
```

- 폰트가 여러개 정의 되어있으면, 왼쪽에서 부터 순차적으로 설치되어 있는 글꼴이 실행된다.

- `font-weight`: 폰트의 굵기를 설정한다.
- `font-style`: 글꼴의 스타일 한다.
- `text-align`: 글꼴 위치를 선택한다.

```html

<style>
    .font_big {
        font-size: 2em;
    }

    .font_italic {
        font-style: italic;
    }

    .font_bold {
        font-weight: bold;
    }

    .font_center {
        text-align: center;
    }

    .font_right {
        text-align: right;
    }
</style>
</head>
<body>

<p class="font_big font_italic font_bold font_center">맨체스터 유나이티드</p>
<p class="font_bold font_right">2024.04.30</p>
<p>'이게 팀이야?' 맨유 재창단하나...유망주 빼고 전부 다 나가!!!!</p>
```

![스크린샷 2024-04-30 오전 10 38 34](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/61378f26-c793-4ee1-a91f-db2c1bed2257)



#### position
- 웹 문서 안 텍스트나 이미지를 원하는 위치로 어떻게 배치할 지를 정하는 속성이다.
   - `static`: 기본값, 다른 태그와의 관계에 의해 자동으로 배치되며 위치를 임의로 설정할 수 없다.
   - `absolute`: 절대 좌표와 함께 위치를 지정한다.
   - `relative`: 원래 있던 위치를 기준으로 좌표를 지정한다.
   - `fixed`: 스크롤과 상관없이 항상 문서 최 좌측 상단을 기준으로 좌표를 고정한다.
   - `inherit`: 부모 태그의 속성값을 상속 받는다.


#### float
- 문서에 사진이나 그림이 있을때, 해당 요소를 어떻게 정렬할지를 정의하는 css 속성이다.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>float_basic</title>
    <style>
        /*사진 왼쪽 정렬*/
        img {
            float: left;
        }
    </style>
</head>
<body>
<img src="../../image/우승.jpeg" height="174" width="290"/>
<p>영국 잉글랜드 그레이터맨체스터 주의 트래포드를 연고로 하는 프로축구 구단이다. 뉴턴 히스 LYR F.C.(Newton Heath LYR F.C.)라는 이름으로 창설되었다. 1902년 4월 26일 지금의 이름인
    맨체스터 유나이티드 F.C.로 개칭 하였고, 1910년에는 홈 경기장을 맨체스터 시 동북쪽의 뱅크 스트리트에서 서남쪽의 올드 트래포드로 이전했다.</p>
<p>잉글랜드 최초의 유러피언컵 우승팀이자, 잉글랜드 클럽 발롱도르 수상자 최다 배출, 그리고 현재 잉글랜드 최상위 프로 축구 리그 최다 우승팀이자, 잉글랜드에서 최초로 트레블 달성 기록을 보유하고 있다. 하지만
    알렉스 퍼거슨 감독이 떠난 이후 각종 문제가 곪아 터지며, 인기와 명성은 여전히 이어갈 지언정 현재는 상당히 몰락한 상황이다.</p>
</body>
</html>
```


![float](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/81c3c9a4-014a-4f4f-83b9-1a4b22615a5a)






