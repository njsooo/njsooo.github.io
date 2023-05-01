---
title: "요소 수직, 수평 중앙 정렬 모음"
categories: UI layout
toc: true
toc_sticky: true
---

## 소개
flex, grid를 사용하지 않고 정렬하는 방법에 대해서 설명하는 글입니다.

## 1. 가로 중앙 정렬

### 1.1 Inline(Inline-block) 요소
부모 요소에 아래의 코드를 적용합니다.
```css
.parent {
  text-align: center;
}
```

### 1.2 1개의 block 요소
block 요소는 width가 auto라면 부모 크기만큼 너비를 차지합니다.  
width를 명시해 여분의 공간을 만든 후 좌우 margin을 주면 중앙 정렬이 됩니다.  
```css
.box {
  width: 100px;
  margin: 0 auto;
}
```

### 1.3 다수의 block 요소

#### 1.3.1 (비추천) 부모 요소에 크기를 지정
요소의 개수 변경에 대처할 수 없습니다.
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="rNqNXeZ" data-user="njsooo" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/njsooo/pen/rNqNXeZ">
  multiple block elements center align by explicitly declaring container width</a> by Jeongsoo Noh (<a href="https://codepen.io/njsooo">@njsooo</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### 1.3.2 (추천) inline-block 이용
요소의 개수 변경에 대처할 수 있습니다.  
요소 사이의 공간이 생기는 이유는 다음과 같습니다.  
요소는 이제 inline-block이고 html에서 태그 사이의 띄어쓰기, 줄바꿈이 영향을 끼치고 있습니다.  
html에서 태그 사이에 공간을 없애거나 CSS에서 negative margin을 이용해 공간을 없앨 수 있습니다.
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="XWxWvgo" data-user="njsooo" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/njsooo/pen/XWxWvgo">
  multiple block elements center align using inline-block</a> by Jeongsoo Noh (<a href="https://codepen.io/njsooo">@njsooo</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 2. 세로 중앙 정렬

### 2.1 한 줄의 글
한 줄의 글의 line-height(행간, 줄 간격)를 높이와 같게 설정해 중앙에 위치하게 합니다.  
폰트는 설계부터 가독성을 위해 글자 위아래에 여분의 공간이 있습니다.  
폰트에 따라 이 공간이 다르므로 정확하게 중앙에 위치하는 것은 아닐 수도 있습니다.  
```css
.item {
  height: 100px;
  line-height: 100px;
}
```

### 2.2 여러 줄의 글
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="MWPYrJV" data-user="njsooo" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/njsooo/pen/MWPYrJV">
  text vertical align using display table</a> by Jeongsoo Noh (<a href="https://codepen.io/njsooo">@njsooo</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

### 2.3 이미지
`img` 태그는 inline 요소라서 `line-height`가 적용됩니다.  
폰트의 descenders 때문에 생기는 빈 공간을 해결하기 위해 부모에 `font-size: 0;`을 적용합니다.
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="qBJEVpY" data-user="njsooo" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/njsooo/pen/qBJEVpY">
  image center align using line-height</a> by Jeongsoo Noh (<a href="https://codepen.io/njsooo">@njsooo</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 3. 가로, 세로 중앙 정렬

### 3.1 absolute, top, left
`top: 50%; left: 50%`는 시작점을 중앙으로 한다는 의미입니다.  
요소를 중앙에 위치하기 위해서 요소 크기의 절반만큼 이동해야 합니다.
```css
.box {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 300px;
  height: 300px;
  background-color: salmon;
  transform: translate(-50%, -50%);
}
```

### 3.2 absolute, top, right, bottom, left
가용 공간을 전체로 하되 너비와 높이를 지정하고 `margin: auto;`를 이용해 중앙 정렬되게 합니다.  
`top: 0; right: 0; bottom: 0; left: 0; `대신 `inset: 0;`을 사용할 수 있습니다.  
```css
.box {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  width: 300px;
  height: 300px;
  margin: auto;
  background-color: salmon;
}
```

### 3.3 display table
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="XWxJzjM" data-user="njsooo" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/njsooo/pen/XWxJzjM">
  center align using display table</a> by Jeongsoo Noh (<a href="https://codepen.io/njsooo">@njsooo</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 참조
[poiemaweb](https://poiemaweb.com/css3-centering)  
[유튜브 빔캠프 CSS](https://www.youtube.com/watch?v=m4v3NRHxOJc&list=PLMv8nY90ATZX3TOLjJaAZsyA8vcNsdX4j)  