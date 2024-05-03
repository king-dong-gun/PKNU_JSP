## JSP 학습 8일차

### HTML 기초 학습

#### css 단위
- `%`, `em`, `rem`등등

##### 적용기준
>부모 요소에 따라 사이즈가 변경되어야 하는 경우
> - em
> - %
 
> 요소의 너비 또는 높이에 따라 사이즈가 변경되어야 하는 경우
> - %
> - viewport 


##### em
```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Em&Rem Study</title>

    <link rel="stylesheet" href="./em.css"/>
</head>
<body>
<div class="level1">
    <h1>Level 1</h1>
    <div class="level2">
        <h1>Level 2</h1>
        <div class="level3">
            <h1>Level 3</h1>
            <div class="level4">
                <h1>Level 4</h1>
            </div>
        </div>
    </div>
</div>
</body>
</html>
```

```css
.level1 {
font-size: 2em;
}

.level2 {
font-size: 2em;
}

.level3 {
font-size: 2em;
}

.level4 {
font-size: 2em;
}
```

![em](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/cc3d9d4b-fd72-4843-bd99-4ced2832ae05)



##### rem
```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Em&Rem Study</title>

    <link rel="stylesheet" href="rem.css"/>
</head>
<body>
<div class="level1">
    <h1>Level 1</h1>
    <div class="level2">
        <h1>Level 2</h1>
        <div class="level3">
            <h1>Level 3</h1>
            <div class="level4">
                <h1>Level 4</h1>
            </div>
        </div>
    </div>
</div>
</body>
</html>
```


```css
.level1 {
    font-size: 32px;
}

.level2 {
    font-size: 32px;
}

.level3 {
    font-size: 32px;
}

.level4 {
    font-size: 32px;
}
```

![rem](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/4e5c9cfb-f20b-4fa4-a816-f7e1c84de45b)




#### flex
- css에서 `display` 속성 중 하나로, **단일 방향 레이아웃**을 작성할 때 사용한다.
  - 기본값은 `rows`
- 자신이 가진 내용물의 `width` 만큼만 차지한다.
- `height`는 컨테이너의 높이만큼 늘어난다.

```html

<div class="container">
    <div class="item1">1번</div>
    <div class="item2">2번</div>
    <div class="item3">3번</div>
    <div class="item4">4번</div>
</div>
```

```css
.item {
    width: 100px;
    height: 100px;
}
```


![flex](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/b07e6e22-f85e-4f53-84c2-32730da61911)


```css
.container {
    display: flex;
}
```

![flex2](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/4995ba5f-79f5-4939-919f-8e9736aba8d3)



- 방향이 `columns`일때
```css
.container {
    display: flex;
    flex-direction: column;
}
```

![flex3](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/c93ad5a9-4766-4aac-af61-079242e0cc33)


```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

![flex4](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/99ab3414-00d8-46e7-9fd2-1ebc001588b8)


- `flex-wrap`: item 줄바꿈 요소
  - `wrap`을 사용하면 플렉스 요소에 여유공간이 없다면 줄바꿈을 한다.



#### grid
- css에서 `display` 속성 중 하나로, **2차원 레이아웃**을 작성할 때 사용한다.
```html
<div class="container">
    <div class="itme1">1번</div>
    <div class="itme2">2번</div>
    <div class="itme3">3번</div>
    <div class="itme4">4번</div>
</div>
```
```css
.container {
    display: grid;
}
```

![grid](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/7ea723aa-8549-4402-b8a3-060722878492)


```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 1fr;
    justify-content: center;
    align-items: center;
}
```
![grid2](https://github.com/king-dong-gun/PKUN_JSP/assets/160683545/7240fc40-67ee-4af3-8090-6133fc8b55e4)

- `grid-template-columns`: 열 크기 정렬
- `grid-template-rows`: 행 크기 정렬
    - `fr`: 사용 가능한 공간에 대한 비율
- `justify-content`: 수평 방향 정렬
- `align-items`: 수직 방향 정렬