---
layout: post
title: HTML/CSS에 대한 기본 지식 - 1주차
tags:
  - HTML
  - CSS
---

## 웹 기초

- 구조 : 웹 콘텐츠에 의미를 부여하고 구조를 형성 → HTML
- 표현 : 시각적인 디자인과 레이아웃 표현 → CSS
- 행위 : 모든 front-end의 브라우저 상호작용을 담당 → JavaScript

## HTML 기본 태그

- https://www.w3schools.com/html/
- http://webberstudy.com/

## CSS:선택자(Selector) 이해

### 1. CSS 선택자(Selector)란?
선택자란 말 그대로 선택을 해주는 요소입니다. 이를 통해 특정 요소들을 선택하여 스타일을 적용할 수 있게 됩니다. 먼저 CSS에서 스타일이 어떤 방식으로 정의되는지 알아봅시다.

#### 1.1 Rule Set

Rule Set(Rule)은 HTML페이지 안의 특정 요소들을 어떻게 렌더링(Rendering) 할 것인지 브라우저에게 알려주는 CSS 문장입니다. 스타일 규칙이라고도 불리는 이 문장은 스타일에 관한 규칙들을 집합처럼 나타냅니다.

![[그림 1] Rule Set](https://github.com/SinamonDev/SinamonDev.github.io/blob/master/_posts/Images/19-01.%20HTML_CSS/rule_set.png?raw=true)

1.2 선택자(Selector)

위쪽 [그림 1]을 다시 보시면, Rule Set 제일 앞 부분의 선택자 요소를 볼 수 있는데요. 왼쪽 중괄호 "{"가 나오기 전의 부분 모두가 선택자입니다. 선택자는 Rule Set의 영향을 받는 HTML페이지 안의 특정 element들을 선택해서 선언 블록(Declaration Block)의 내용을 적용시켜 줍니다.