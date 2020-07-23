---
layout: post
title: 티릴리의 Ground Rule
tags:
- Rule
- Culture
hidden: true
---

티릴리에서 업무효율을 위해 정한 Ground Rule에 대해서 설명합니다! :)

# 기본사항 

1. 출근 : 10시 ~ 11시
2. 점심시간 : 13시 ~ 14시
3. 퇴근시간 : 출근 시간으로 부터 9시간 뒤 자율퇴근
4. 호칭 : 상호간에 ~님 호칭

<br/>

# 깃헙

## Git Flow

### TS - Flow (티릴리 솔로 플로우)   

```
master - develop - hotfix/ - hotfix-작업단위
```

### TC - Flow (티릴리 콜라보 플로우)    

```
master - develop - feature/ - feature-작업단위
                            - hotfix/ - hotfix-작업단위
```

<br/>

## Commit Message Rule

### 개요

#### 커밋 제목 : `[ 작업 액션 ]` `[ 작업 단위 ㄴ]`
  * `[( Init, Add, Fix, HotFix, Improve, ...)]` 중 택일 + `[ 작업 단위에 대한 개요 ]`

#### 커밋 설명 : 설명
  * `[설명]` : 추가 상세 설명 내용은 커밋 제목 하단에 내용으로 추가한다

#### 작업 액션

- `Init` : 해당 작업을 **처음 시작** 할 때 또는 해당 작업에 대한 **커밋을 처음 진행** 할 때
- `Add` : 이미 해당 작업에 대한 INIT 이 이뤄지고 난 뒤 **새로운 무언가를 추가** 할 때 (기능, 디자인 등을 추가할 때)
- `Fix` : 기존의 작업 내용을 **수정해야 할 때** (기능, 디자인 등을 수정할 때)
- `HotFix` : 이미 배포된 작업에 대해 **급하게 수정**을 해야할 때, 즉 최고 우선순위의 Fix 작업
- `Imporve` : 기존의 작업 내용을 고치는 개념이 아니라 **향상시키고자 할 때** (코드 최적화, 쿼리 최적화, 기능 개선, 디자인 개선)

### 예시

- Init 패션 태그 뷰셋
- Add 소셜로그인 Facebook API
- Fix Facebook 소셜로그인 Email Field validation 오류
- HotFix 소셜 계정 이미지 does not exist 오류
- Improve 도시락 태그 api 쿼리 코드 리팩토링

### 과정

``` bash
$> git add -p
$> git commit -v
$> git push origin {branch}
```

#### git add -p

코드 **블럭 단위** 또는 **파일 단위** 로 add 를 할 수 있는 옵션 (CLI)         
- y : 해당 hunk 를 add        
- n : 해당 hunk 는 스킵       
- q : 그만두기        
- a : 해당 파일 전체를 add        
- d : 해당 파일 전체를 스킵       

#### git commit -v  

- 커밋을 vi 에디터로 진행하는 옵션        
- 첫번째 줄은 title 두번째 줄부터 설명     

<br/>

# 트렐로

## 개념정리

1. 보드란 트렐로의 create board 를 통해 생성되는 보드를 의미한다.
2. 칸반이란 트렐로의 add another list 를 통해 생성되는 하나의 리스트를 의미한다.
3. 카드란 하나의 리스트 안에 있는 하나의 아이템을 의미한다.


## 규칙

1. 보드는 프로젝트 단위로 생성
2. 칸반은 Todo, WIP, Done, HotFix 4 개로 구성함
3. 카드는 기획자가 제공한 화면설계서의 Index 를 기준으로 구성함
4. 각 카드는 아래의 카드 규칙에 의해 운영함

## 카드규칙

### 구성

#### Description

1. 개요 : 각 페이지에 대해 개발자가 이해한 간단한 설명 제시
2. 상세사항 : 개요에 제시된 기능들에 대한 상세 설명
3. 프론트엔드 컴포넌트 : 페이지를 컴포넌트 단위로 구성하고 해당 컴포넌트의 목차를 제시
4. 백엔드 기능 : 페이지 내 기능을 목차로 제시
5. 외부 API : 외부 API 가 필요할 경우 해당 API 의 목차를 제시

#### Checklist

1. 프론트엔드 체크리스트 : Description 상의 컴포넌트를 기준으로 작업 단위를 나눠 체크리스트로 기록
2. 백엔드 체크리스트 : Description 상의 백엔드 기능을 기준으로 작업 단위를 나눠 체크리스트로 기록

### 예시

```
# 설명

## 개요
보관소 리스트 페이지로서 메인 페이지로부터 검색된 내용을 바탕으로 보관소 리스트 및 구글 지도를 렌더링한다.

## 상세사항
* 경로 : '/store/'
* 구글맵 : 구글맵 api 를 연동하여 자바스크립트로 맵을 렌더링한다.
* 검색 옵션 없이 바로 검색페이지로 진입 시 default 로 서울시 지역의 보관소를 리턴

## 프론트엔드 컴포넌트
- google map
- store list card
- search form

## 백엔드 기능
- get store search result

## 외부 API
- Google Map
  - 구글 지도 객체 생성 : new google.maps.Map({element})
  - 지도 내의 툴팁 객체 생성 : new google.maps.InfoWindow()


# 체크리스트

## 프론트엔드
> google map render
> google map marker
> store list card ui & action
> search form
> search result list

## 백엔드
> 검색된 지역 보관소 리턴
```

<br/>

# 코드 컨벤션

## Django

- import는 **알파벳 순** 으로 정렬한다.

```python
# python의 Library
import base64

# Django, DjangoRestFramework 등의 Library 순서
from django.db import models
from django.db.models import (
			Q, 
			OuterRef, 
			Subquery,
		)

from rest_framework.authtoken.models import Token

# 자신이 만든 Third party app
from apps.account.models import Profile
from apps.snippet.models import Snippet
```

- Class = Carmel Case, Extra = Snake Case

```python
# Carmel Case
class CultureTag(models.Model):
	nickname = models.Charfield('닉네임', max_length=127, blank=True, null=True)

	# Snake Case
	def get_nick_name(self):
		return self.nickname
```

- filter와 get의 결과에 대한 변수명은 아래와 같이 작성하며, 3개 이상의 파라미터가 필요한 경우 띄어쓰기를 진행한다.
- 3개 이상의 파라미터가 있어 tuple로 작성한 경우 마지막에 **,** 를 작성한다.

```python
snippet_qs = Snippet.objects.filter(
								like=True,
								post__id=1,
								user=user, # , 붙음
							)

# 단 get을 사용할 때는 Error를 주의하자
snippet = Snippet.objects.get(id=10)
```

- kwargs.get 에 default 설정하고 `''`대신 `None`을 사용한다.

```python
user = kwargs.get('user', None)
```

- Class 사이는 2번, Class 내의 함수에서는 1번 띄어쓴다.

```python
from django.db import models
# 2칸 띄어쓰기

class A(models.Model):
	# 1칸 띄어쓰기
	def a(self):
		pass
# 2칸 띄어쓰기

class B(models.Model):
	pass
```

- Static, Media 파일을 project 밖으로 꺼내고 저장소에 올리지 않는다.

- log는 한글로 명시하며, print를 이용하여 각 def마다 디테일하게 설정하고, uwsgi에서 찍힌 로그를 확인한다.
	- log를 찍는 목적은 이후 서비스 중 에러가 일어났을 때 해당 과정을 트래킹하기 위해서이다.
	- 때문에 어떤 함수가 실행되었는지 작게는 어떤 기능이 일어나고 있는지를 명시해야한다.
	- Data가 변경되는 Create, Update, Delete 앞, 뒤로는 log가 필요하며, 어떤 데이터 값이 어떻게 변경되어지는지 상세한 로그를 기록해야한다.

## React

<br/>

<!--
# Code Review

## 일자

- 매주 금요일 
- 단 자신이 원할 때 리뷰어의 동의하에 코드 리뷰를 동적으로 진행 가능

## 리뷰 시 주로 봐야할 기능

- 미리 발견하는 버그
- 삽질 회피 코드의 공유
- 더 나은 로직의 제안
- 더 나은 변수명 제안
- 예외 처리
- 버그 발생 가능성
- 병목 발생 가능성

## 리뷰어의 자세

- 의견을 잘 청취
- 의도를 잘 설명
- 결정은 개발자가
- 만약 마음에 많이 들지 않으면 직접 수정
-->
