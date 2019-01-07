---
layout: post
title: HTML/CSS에 대한 기본 지식 - 1주차
tags:
  - HTML
  - CSS
---

시나몬에서 진행한 **디자이너를 위한 HTML/CSS 스터디**에서 진행한 내용을 정리했습니다.

## 웹 기초

- 구조 : 웹 콘텐츠에 의미를 부여하고 구조를 형성 → HTML
- 표현 : 시각적인 디자인과 레이아웃 표현 → CSS
- 행위 : 모든 front-end의 브라우저 상호작용을 담당 → JavaScript

## HTML 기본 태그

- [w3schools](https://www.w3schools.com/html/)
- [webberstudy](http://webberstudy.com/)

## CSS:선택자(Selector) 이해

### 1. CSS 선택자(Selector)란?
선택자란 말 그대로 선택을 해주는 요소입니다. 이를 통해 특정 요소들을 선택하여 스타일을 적용할 수 있게 됩니다. 먼저 CSS에서 스타일이 어떤 방식으로 정의되는지 알아봅시다.

#### 1.1 Rule Set

Rule Set(Rule)은 HTML페이지 안의 특정 요소들을 어떻게 렌더링(Rendering) 할 것인지 브라우저에게 알려주는 CSS 문장입니다. 스타일 규칙이라고도 불리는 이 문장은 스타일에 관한 규칙들을 집합처럼 나타냅니다.

![[그림 1] Rule Set](https://github.com/SinamonDev/SinamonDev.github.io/blob/master/_posts/Images/19-01.%20HTML_CSS/rule_set.png?raw=true)

#### 1.2 선택자(Selector)

위쪽 그림을 보면, Rule Set 제일 앞 부분의 선택자 요소를 볼 수 있는데요. 왼쪽 중괄호 "{" 가 나오기 전의 부분 모두가 선택자입니다. 선택자는 Rule Set의 영향을 받는 HTML페이지 안의 특정 element들을 선택해서 선언 블록(Declaration Block)의 내용을 적용시켜 줍니다.

### 2. 선택자(Selector)의 종류

#### 2.1 전체 선택자(Universal Selector)

#### 2.2 태그 선택자(Type Selector)

#### 2.3 클래스 선택자(Class Selector)

#### 2.4 ID 선택자(ID Selector)

#### 2.5 가상 클래스 선택자(Pseudo-Classes)

#### 2.6 복합 선택자(Combinator)

#### 2.7 속성 선택자(Attribute Selectors)

### 3. CSS 주요 스타일 속성

| 스타일 | 설명 | 비고 |
|:-----|:----:|-----:|
| color  | 글자색  | CSS 색상명 또는 16진 색상값  |
| font-size  | 글자크기  | 값 지정(단위 : px, em)  |
| font-family  | 글자폰트  | tordkdk  |
| text-align  | 텍스트 수평 정렬  | center, left, right  |
| text-decoration  | 글자에 줄긋기  | none, underline, line-through, overline  |
| text-transform  | 대소문자 변경	  | uppercase, lowercase, capitalize  |
| background-color  | 배경색  | CSS 색상명 또는 16진 색상값  |
| margin  | 여백 (바깥쪽) | auto 또는 값 지정(단위: px) |
| margin-top<br>margin-bottom<br>margin-left<br>margin-right<br>  | 한쪽 여백  | auto 또는 값 지정(단위: px) |
| padding  | 여유공간 (안쪽)  | 값 지정(단위: px)  |
| width  | 너비  | 값 지정(단위: px, %, vw)  |
| height  | 높이  | 값 지정(단위: px, %, vh)  |
| border  | 외곽선  |   |
| border-top<br>border-bottom<br>border-left<br>border-right  | 한쪽 외곽선  |   |
| border-radius  | 모서리 둥글게  | 값 지정(단위: px 또는 %)  |
| border-color  | 외곽선 색상  | CSS 색상명 또는 16진 색상값  |
| border-width | 외곽선 두께  | 값 지정(단위: px)  |
| border-style  | 외곽선 스타일	| dashed, dotted, outset, solild|
| border-top-left-radius<br>border-top-right-radius<br>border-bottom-left-radius<br>border-bottom-right-radius | 한쪽 모서리 둥글게 | 값 지정(단위: px 또는 %) |
| display  |   | block, inline-block, inline, none  |
| float | 좌, 우측 정렬 | left, right |
| clear |  | 	left, right, both |
| position |  | absolute, relative, fixed |
| z-index | 뷰 우선순위 | 양의 정수값 |
| opacity | 투명도 | 0.0(완전 투명) ~ 1.0(완전 불투명), initial, inherit |

## 참고

- http://www.nextree.co.kr/p8468/