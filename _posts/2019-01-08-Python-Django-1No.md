---
layout: post
title: Python/Django 입문 스터디 - 1회차
tags:
  - Python
  - Django
  - Backend
---

시나몬에서 진행한 **Python/Django 입문 스터디**에서 진행한 내용을 정리했습니다.


## 각자 아이디어 정리

- 박운철 :
- 이재연 :

<br/>

## 팀매칭

### 팀 1
- 박운철

### 팀 2
- 이재연
<br/>

<br/>

## Django 목차

- Django란?
- 왜 장고를 사용할까?
- MTV Architecture
- 개발 환경 설정
- 개발 툴
- Git

<br/>

### Django란?

Djang란 보안이 우수하고 유지보수가 편리한 웹사이트를 **신속하게 개발하도록 도움을 주는 파이썬 웹 서버 프레임워크** 입니다.

관리자 페이지 (Django의 강력한 기능 중 하나), 로그인, 회원가입, 인증 기능 등 다양한 기능들을 제공합니다.

> +) 프레임워크란? <br/>
소프트웨어의 구체적인 부분에 해당하는 설계와 구현을 재사용이 가능하게끔 일련의 협업화된 형태로 클래스들을 제공하는 것

<br/>

### Django의 장점

#### 1. Complete (완결성 있는)

**Batteries Included** 라는 철학이 있습니다. 전자 제품을 구입하여 포장을 풀면 배터리가 패키지에 포함되어있어, 즉시 사용할 수 있는 것을 빗댄 철학입니다.

Django는 이 철학을 따르기 때문에 즉시 재사용할 수 있는 소프트웨어 패키지 & 모듈 제공을 목표로 나아가고 있습니다.

#### 2. Scalable (확장성 있는)

Django는 Component 기반의 **shared-nothing architecture** 를 사용합니다.

Shared-Nothing이란 각각의 아키텍처가 독립적이어서 필요하다면 교체 및 변경할 수 있다는 이야기입니다.

즉 Caching Server, Database Server, Application Server 등 각 부분이 분명히 구분되면, 하드웨어를 추가해서 발생하는 늘어난 Traffic에 대응해 크기를 변경하기 쉽습니다.

#### 3. Maintainable (유지보수가 쉬운)

Django는 유지보수가 쉽고 재사용하기 좋게하는 디자인 원칙과 패턴들을 이용하여 작성되었습니다. **Don't Repeat Yourself (DRY)** 원칙을 적용해서 불필요한 중복이 없게끔 개발하여, 코드의 양을 줄였습니다.

<br/>

### Django를 사용하는 웹사이트들!

Django는 `Youtube`, `DropBox`, `Google`, `Instagram`, `Pinterest`에서 사용되고 있습니다. 즉, Django를 사용하여 대량의 트래픽 처리가 가능하며, 이에 걸맞는 성능을 낼 수 있다는 것을 증명해보이고 있습니다.


#### +) [현재 인기 있는 Framework 순위](http://hotframeworks.com/)

#### +) Python은?

Python 또한 다양한 분야에서 사용되며, 점차 그 중요성이 커지고 있습니다.

현재 Python은

1. Data Science(Numpy, 사이킷런, Tensor Flow, Keras, pyTorch…)
2. 웹스크롤링 (BeatifulSoup)
3. 빌드 시스템(SCons), 빌드 보조 툴로 펄에서 파이썬으로 변경되고 있습니다.

등의 분야에서 사용되고 있습니다.

#### +) Python + Django 공부

- https://dojang.io/course/view.php?id=7
- https://djangogirls.org/
- https://developer.mozilla.org/ko/docs/Learn/Server-side/Django/Introduction
- https://www.askcompany.kr/ (유료)

<br/>

### Django의 특징

#### MTV Pattern

패턴을 사용하는 이유는 코드의 복잡성을 줄이고, 재사용성을 높이기 위해서 입니다.
**MVC패턴** 이라는 패턴이 그나마 제일 많이 들어본 패턴 중 하나였던 것 같습니다.

Model, View, Controller로 구성된 패턴입니다.
- Model : Database
- View : 사용자가 보게 될 화면의 모습
- Controller : 어플리케이션의 제어 흐름 및 처리 로직을 정의

하지만 Django는 **MTV패턴** 을 사용합니다. MVC와 아주 조금 다를 뿐, 거의 비슷합니다.

- Model : Databse
- Template : 사용자가 보게 될 화면의 모습
- View : 어플리케이션의 제어 흐름 및 처리 로직을 정의

Django에는 이런 패턴이 있다는 것만 알아두면 후에 Django를 실습하면서 이 패턴에 대해서 느낄 수있을 것입니다! :)

#### ORM(Object Relational Mapping)?

객체 간의 관계가 정의되어있어, SQL문을 쓰지 않고, 데이터 CRUD(Create/Retrieve/Update/Delete)를 수행할 수 있는 것입니다.

기존에는 Database에 데이터가 존재하고, 해당 데이터의 CRUD를 실행하려면 SQL문을 실행해야했습니다. 하지만 Django를 사용하면, ORM을 이용하여 객체로 데이터 테이블을 정의하고 해당 테이블에서 데이터 관련 처리를 진행할 때도, 객체로 접근하면 되기 때문에, 더욱 편리하게 사용할 수 있습니다.

이와 관련된 내용은 Model을 공부하면서 더욱 쉽게 알 수 있습니다. :)

<br/>

### Django 코드 흐름

Django가 어떻게 동작하는지 일련의 과정을 살펴봅시다.

<img src=""/>

처음에 User가 우리가 개발한 웹사이트에 들어갑니다. 그리고 login과 같은 기능을 사용하며 우리에게 요청을 하게 됩니다. (Request)

해당 요청을 Url이 받아서 어떤 View를 실행시켜야하는지 판단합니다.

View에서 해당 요청에 관련된 응답을 만드는 중 데이터를 가져오는 등 Model에 접근이 필요하다면 Model부분으로 가게됩니다. html페에지를 로딩해야한다면, Template쪽으로 가게됩니다.

Model에서 Database에 있는 데이터를 조회/수정/삭제/입력 등 데이터 관련된 처리를 하게 됩니다.

그리고 해당 흐름을 반대로 진행하며 User에게 Response를 전달하게 됩니다.

<br/>

### 개발 환경 설치

[Django Girls 설치하기](https://tutorial.djangogirls.org/ko/installation/)를 참고하여 각 OS에 맞게 환경을 설치하면 됩니다.

버전은 최신 버전으로 진행하며 pip이 최신버전이라면  `$ pip install django~=1.11.0`으로 뒤에 django Version을 설정하는 것이 아니라. `$ pip install django` 만으로도 pip이 알아서 최신버전의 Django를 설치줍니다.

추가적인 Django의 Version은 [Django Version 확인하기](https://www.djangoproject.com/download/) 이곳을 확인하시면 됩니다! :)

<br/>

### 개발툴

보통 저는 `Visual Code`를 사용하지만 많은 Django 개발자들은 Python에 특화된 강력한 툴인 `PyCharm`을 사용합니다. `Sublime`을 사용하기도 하지만 추천하지는 않습니다.

<br/>

### Django 시작하기

`$ mkdir djangoprj` : mkdir이란 `make directory`즉 폴더를 생성한다는 뜻입니다. 이 command를 이용하여 djangoprj이라는 폴더를 생성합니다.

`$ cd djangoprj` : cd란 `change directory` 즉 해당 폴더로 이동한다는 뜻입니다. 이 command를 이용하여 djangoprj이라는 폴더로 이동합니다.

`$ python3 -m venv 가상환경이름` : 해당 명령어를 사용하여 가상 환경을 생성합니다.

`$ source 가상환경이름/bin/activate` : 해당 가상 환경을 실행합니다.

`$ pip3 install django` : django를 설치합니다.

`$ django-admin startproject 프로젝트이름 .` : 프로젝트를 현재 경로에 생성합니다. (뒤에 .을 빼면 현재 경로로 생성되지 않습니다.)

̀`$ python3 manage.py makemigrations` : 마이그레이션 파일 (초안) 생성하는 명령어입니다. django에서는 기본적으로 정의되어있는 model이 있기 때문에 해당 model을 적용해주어야합니다.

`$ python3 manage.py migrate` : 해당 마이그레이션 파일을 DB에 반영합니다.

`$ python3 manage.py runserver` : 해당 프로젝트를 실행합니다. 기본 ip는 127.0.0.1이고 port는 8000입니다.

웹사이트에 들어가서 `127.0.0.1:8000` 을 실행하면 실행한 django 프로젝트가 보이게 됩니다.

#### +) 가상 환경이란?
여러개의 파이썬 프로젝트가 하나의 컴퓨터에서 충돌을 일으키지 않고 존재할 수 있도록 도와줍니다.

<br/>

### 각 파일 살펴보기

- __init__.py : 빈 파일입니다. 이 파일은 Python에게 이 디렉토리를 하나의 Python 패키지로 다루도록 지시합니다.
- settings.py : 웹사이트의 모든 설정을 포함하고 있습니다. 
- urls.py : 사이트의 url와 뷰의 연결을 지정해줍니다. 여기에는 모든 url 매핑 코드가 포함될 수 있지만, 특정한 어플리케이션에 매핑의 일부를 할당해주는 것입니다.
- wsgi.py : 당신의 장고 어플리케이션이 웹서버와 연결 및 소통하는 것을 돕습니다.
- manage.py : 이 스크립트는 어플리케이션을 생성하고, 데이터베이스와 작업하고, 그리고 개발 웹 서버를 시작하기 위해 사용합니다.

#### +)wsgi.py란?

웹서버와 파이썬을 사용한 웹 어플리케이션 개발환경 간의 인터페이스에 대한 규칙입니다. 좀더 자세한 내용은 [WSGI란 무엇인가?](https://juliahwang.kr/network/2017/09/17/WSGI%EB%9E%80%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80.html)을 참고하면 됩니다.

<br/>

### Git

Git은 너무 복잡하고 설명하려면 한 페이지가 더 필요하기 때문에 [깃, 깃허브 강의 - 구조 및 간단한 버전 관리 예제](https://www.youtube.com/watch?v=ImatGhE_9Ho)로 대체하겠습니다.
