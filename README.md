# CSS 기초

## 섹션 0

### 1. CSS란?

CSS = Cascading Style Sheets </br>

Cascading = 계단식 </br>
Style = 멋을 내다 </br>
Sheets = (종이) 한 장 </br>

- 계단식으로 스타일을 정의하는 문서
- CSS는 HTML 문서에 스타일을 더해줌

## 섹션 1

### 1. 기본 문법

- 선택자 : 어떤 요소에 스타일을 적용할지에 대한 정보
- 중괄호 : 선택한 요소에 적용할 스타일을 정의하는 영역
- 속성명 : 어떤 스타일을 정의하고 싶은지에 대한 정보 (색상, 크기 등)
- 속성값 : 어떻게 정의하고 싶은지에 대한 정보
- 주석 : /\*\*/

```
p { color: red; }
```

p는 선택자, {} 안에 내용이 들어가고, color는 속성명이며 red는 속성값

### 2. HTML에 CSS 적용하기

<u>인라인 스타일</u>

```
`<div style="color: blue;"></div>`
```

<u>스타일 태그</u>

```
`<head><style></style></head>`
```

<u>문서 연결</u>

```
`<head><link href="style.css" rel="stylesheet"></head>`
```

### 3. CSS 선택자

- 전체 선택자 : \*
- 태그 선택자 : tag {}
- 클래스 선택자 : .class {}
- 아이디 선택자 : #id {}

### 4. CSS 속성 : 텍스트 꾸미기

<u>font-family</u> : sans-serif, monospace, etc.

```
* { font-family: Times, monospace, serif; }
```

<u>font-size</u> : px(절대값), rem(html 태그 기준), em(부모요소 기준)

```
p { font-size: 32px; }
```

<u>text-align</u> : left/right, center, justify(양끝 정렬)

```
p { text-align: justify; }
```

<u>color</u>: name, hexcode, rgb

```
span { color: red; }
span { color: #FF0000; }
span { color: rgb(100%, 0%, 0%); }
```

### 5. CSS 속성 : display, border

<u>display</u>

```
div { dipsplay : block; }
```

<u>border</u> (border-width, border-style, border-color를 정의하는 단축 속성)

```
div { border: 2px solid green; }
```

### 6. CSS Box Model

#### (1) 소개

브라우저가 요소를 렌더링 할 때 각각의 요소는 사각형 형태로 영역을 차지 </br>
이 영역을 '박스'라 하며 CSS는 박스의 크기, 위치, 속성(색, 배경, 테두리 등)을 결정 </br>
박스는 컨텐츠 영역, 안쪽 여백, 바깥 여백, 경계선으로 구성 </br>
각각의 크기는 컨텐츠 영역(width, height), 안쪽 여백(padding), 바깥 여백(margin), 경계선(border-width)으로 지정 </br>

#### (2) 여백 : margin, padding

<u>margin</u> : margin, margin-top/right/bottom/left
<u>padding</u> : padding, padding-top/right/bottom/left

#### (3) box-sizing

box-sizing 속성은 요소의 너비와 높이의 계산 방법 지정 </br>

<u>content-box</u> : 기본값; 너비와 높이가 컨텐츠 영역만을 포함
<u>border-box</u> : 너비와 높이가 안쪽 여백과 테두리까지 포함

#### (4) background

background는 컨텐츠의 배경을 정의하는 단축 속성 </br>

- background-color : 배경 색
- background-image : 배경 이미지 지정
- background-position : 배경 이미지 초기 위치 정의
- background-size : 배경 이미지 크기
- background-repeat : 배경 이미지 반복

### 7. CSS 속성 : float, clear

- float은 요소를 문서의 일반적인 흐름에서 제외시켜 자신을 포함하는 컨테이너의 왼쪽 또는 오른쪽에 배치

```
div { float: none; }
div { float: left; }
div { float: right; }
```

- clear는 float 요소 이후에 표시되는 요소가 float을 해제하여 float 요소의 아래에 배치

```
div { clear: none; }
div { clear: left; }
div { clear: right; }
div { clear: both; }
```

### 8. CSS 속성 : position (with top/right/bottom/left)

position은 문서 상 요소를 배치하는 방법을 결정 </br>
position이 요소 배치 방법을 결정하면 top, right, bottom, left가 최종 위치 결정 </br>

```
div { position: static; } : 기본값; 문서 흐름에 따라 배치
div { position: relative; } : 문서 흐름에 따라 배치하되 상하좌우 위치 값에 따라 오프셋 적용
div { position: absolute; } : 문서 흐름에서 제거하고 (코드 상) 가장 가까운 position 지정 요소에 대해 상대적 오프셋 적용
div { position: fixed; } : 문서 흐름에서 제거하고 절대적 지정 위치에 고정
div { position: sticky; } : 스크롤 이동으로 요소가 움직여도 sticky 요소는 고정된 상태 유지
```

### 9. Flexbox

박스 내 요소 간 공간 배분과 정렬 기능을 제공하기 위한 1차원 레이아웃 모델 </br>
한 번에 행 또는 열만을 다룸 </br>
flexbox는 flex container라고도 하며 `display: flex;`를 통해 적용 </br>
주축과 교차축이 있으며, `flex-direction: value`를 통해 주축과 방향을 결정 </br>

- flex-direction : 주축 방향
  - row
  - row-reverse
  - column
  - column-reverse
- justify-content : 주축 배치
- align-items : 교차축 배치
- align-self : 교차축 개별 요소 배치
- flex-wrap : 줄바꿈 여부

<hr>
<hr>

## CSS Reference

### CSS Selector Reference

**Reference** : https://www.w3schools.com/cssref/css_selectors.php

### CSS Property Reference

**Reference** : https://www.w3schools.com/cssref/index.php
