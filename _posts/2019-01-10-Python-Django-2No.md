---
layout: post
title: Python/Django 입문 스터디 - 2회차
tags:
- Python
- Django
- Backend
---

안녕하세요! :)

오늘은 장고 걸스 튜토리얼을 보면서 따라해보는 라이브 코딩시간을 가졌습니다.

다들 처음에는 느리지만, 이후에 조금 익숙해지시면 점점 빨라지는 것을 느끼실 수 있을 것입니다! :)

오늘한 내용과 간단한 개념들 그리고 심화 내용을 정리해보도록 하겠습니다.

<br/><br/>

### Django 흐름 이해하기

![[그림 1] Django 코드 흐름](https://github.com/SinamonDev/SinamonDev.github.io/blob/master/_posts/Images/19-01/django-working-flow.png?raw=true){: width="400px"}

이 그림을 확인한 후 개발을 진행하면 더욱 개발이 편리해집니다.

사용자가 **URL** 을 치면 Url에 있는 **View** 로 가고 View에서 **Model** 로 접근하여 데이터를 얻어옵니다. 

데이터를 얻어온 후 가져온 데이터를 View로 가져가고, View는 **Template** 에 해당 데이터를 주고 Template은 해당 데이터를 화면에 보여줍니다.

이 흐름을 이해하시면, 원하는 페이지를 개발할 때 어떤 순서로 개발해야할지가 눈에 보이게 됩니다.

<br/><br/>

### 프로젝트 및 가상 환경 생성하기

`$ mkdir djangoprj` : mkdir이란 `make directory`즉 폴더를 생성한다는 뜻입니다. 이 command를 이용하여 djangoprj이라는 폴더를 생성합니다.

`$ cd djangoprj` : cd란 `change directory` 즉 해당 폴더로 이동한다는 뜻입니다. 이 command를 이용하여 djangoprj이라는 폴더로 이동합니다.

`$ python3 -m venv 가상환경이름` : 해당 명령어를 사용하여 가상 환경을 생성합니다.

`$ source 가상환경이름/bin/activate` : 해당 가상 환경을 실행합니다. (앞에 `(가상환경이름)` 이 붙으면 현재 가상 환경 안으로 들어왔다는 의미가 됩니다.)

`$ pip install --upgrade pip` : pip을 최신 버전으로 업그레이드 시켜줍니다.

`$ pip install django` : django를 설치합니다. ([Django Version 확인하기](https://www.djangoproject.com/download/))

`$ django-admin startproject 프로젝트이름 .` : 프로젝트를 현재 경로에 생성합니다. (뒤에 .을 빼면 현재 경로에 생성되지 않습니다. 현재 경로에 생성되지 않아도 괜찮지만 보통은 현재 경로에 생성되도록 **.** 을 사용합니다.)

`$ python3 manage.py makemigrations` : **마이그레이션 파일(초안) 생성** 하는 명령어입니다. 아직 모델을 만들지 않았지만, django에서는 기본적으로 정의되어있는 model이 있기 때문에 해당 model을 적용해주어야합니다.

`$ python3 manage.py migrate` : 해당 마이그레이션 파일을 DB에 반영합니다.

`$ python3 manage.py runserver` : 해당 프로젝트를 실행합니다. 기본 ip는 127.0.0.1이고 port는 8000입니다.

웹사이트에 들어가서 `127.0.0.1:8000` 을 실행하면 실행한 django 프로젝트가 보이게 됩니다.

현재 웹사이트에서 귀여운 우주선이 날아다니면서 성공했다는 표시가 뜨면 성공입니다! :)

( **프로젝트 안에 있는 settings.py의 DEBUG=TRUE 일때 즉 개발환경일 때만 이 화면이 보입니다.** )

<br/>

#### +) pip이란 무엇인가?

pip는 **Python Package Index (PyPI) 저장소** 로부터 파이썬 패키지를 받아 설치하는 **패키지 관리 도구** 입니다.

PyPI란 (가끔 The Cheeseshop 이라고도 불리는)는 **third-party 파이썬 오픈소스 패키지들을 위한 저장소** 입니다.

즉 pip은 _PyPI에 있는 third-party 패키지를 설치하고 관리해주는 패키지 관리 도구_ 입니다.

pip에도 버전이 있기 때문에 pip의 버전도 고려해서 설치를 진행해야합니다. 

<br/>

#### +) 가상 환경을 왜 사용하는가?

보통 여러개의 파이썬 프로젝트가 하나의 컴퓨터에서 충돌을 일으키지 않고 개발할 수 있도록 가상환경을 이용해서 환경을 구분하기 위해 사용합니다.

<br/><br/>

### app 생성하기

`$ python manage.py startapp 앱이름` : 앱을 생성합니다.

이후부터는 [django girls tutorial](https://tutorial.djangogirls.org/ko/)을 따라하시면 됩니다. 

[github](https://github.com/django-study-1st/django-girls-tutorial)에 코드를 올려놓았으니 참고하시면 됩니다. 

<br/><br/>

## 추가 간단한 개념

코딩을 진행하면서 필요한 개념을 간단하게 정리하였습니다.

<br/>

### makemigrations? migrate?

Django는 DB에 적용하기 전 **migration file** 을 생성합니다. (`makemigrations`)

이 migration file을 읽어서 DB에 적용이 되게 됩니다. (`migrate`)

즉 model을 생성하면 꼭!! 

`$ python manage.py makemigrations` 

`$ python manage.py migrate` 를 진행하여 생성한 모델은 DB에 적용시킬 수 있도록 합니다.

<br/>

#### [TIP](https://wayhome25.github.io/django/2017/03/20/django-ep6-migrations/)

- `$ python manage.py makemigrations [app-name]` 과 같이 App name을 명시하여 예상치 못한 migration을 방지할 수 있습니다.
- `$ python manage.py showmigrations` 를 통해서 **적용 상태를 조회** 할 수 있습니다. ([x] : 적용 후 []: 적용 전)
- **이미 적용한 migration 파일은 절대로 지우면 안됩니다.**
- `no such table` , `column` 등의 오류가 보이면 migration 대부분이 migration오류이니, migration을 진행해주시면 됩니다.

<br/><br/>

### static? media?

`static` 이란 정적인 데이터 즉 웹서비스를 진행하면서도 변경되지 않을 데이터를 의미합니다. 예를 들어 css 파일의 경우 웹서비스가 제공될 때 변경되지 않는 데이터 이기 때문에 `static` 으로 분류됩니다.

`media` 란 정적인 데이터이나, 동적으로 변경될 수 있는 데이터 입니다. 예를 들어 이미지를 업로드 시키면 이미지는 정적인 데이터이나, 언제든 변경되거나, 추가, 삭제 될 수 있기 때문에 이는 `media` 로 분류됩니다.

<br/><br/>

### Form이란?

Form이란 `HTML 폼(Form) 은 웹 페이지상에서 한개 이상의 필드나 위젯들의 묶음을 말하며, 사용자로부터 정보를 수집하여 서버에 제출하는데 사용된다.` 라고 정의되어 있습니다. 

HTML에서 원래 Form을 생성하려면 아래와 같은 코드가 필요했습니다.

```html
<form action="/team_name_url/" method="post">
<label for="team_name">Enter name: </label>
<input id="team_name" type="text" name="name_field" value="Default name for team.">
<input type="submit" value="OK">
</form>
```

위의 코드에서는 현재 team name을 text type 으로 받고 있고 submit 버튼을 누르면 POST method로 해당 데이터가 전송되는 것을 볼 수 있습니다.

Django는 위와 같이 form을 생성하는 수고를 덜어주기 위하여 Form Class을 정의하고, 해당 Form을 아래와 같은 형식으로 코딩하면 정상적으로 동작하도록 개발하였습니다. Form Class를 생성해주고 해당 html에서 아래와 같이 써주면 위의 html과 같은 형식으로 변환됩니다.

```python
{{ form.as_p }}
```

form을 개발하고 웹에 해당 페이지를 띄운 후 크롬의 `Settings > More Tools > Developer Tools` 에 가셔서 `Sources` 탭에 해당 웹페이지의 소스를 보시면 위의 html과 같은 코드를 확인하실 수 있습니다.

<br/><br/>

### Foreign Key? Primary Key?

**Primary Key** 란 `일반적으로 테이블의 각 행을 고유하게 식별하는 값을 가진 열` 이라는 정의를 가지고 있습니다.

만약 `name=이재연 nickname=닉네임` 라는 계정이 존재하고 있다고 가정합니다.

하지만 이름과 닉네임은 같지만 다른 사람인 이재연이 계정을 생성하려고 했을 때 (`name=이재연 nickname=닉네임`) 현재의 필드값으로는 어떤 사람이 어떤 이재연인지 구분할 수 없게 됩니다.

따라서 보통 ID를 Primary Key로 두어 구분하는데 예를 들어 먼저 온 이재연을 `id=1 name=이재연 nickname=닉네임`이라고 하고 뒤에 온 이재연을 `id=2 name=이재연 nickname=닉네임` 라고 하면 두 개의 값이 명확하게 구분됩니다.

이처럼 해당 필드를 구분하기 위해 있는 고유값을 Primary Key라고 하고 위의 예제에서는 ID가 Primary Key가 됩니다.

<br/>

**Foreign Key** 란 `두 테이블의 데이터 간 연결을 설정하고 강제 적용하여 외래 키 테이블에 저장될 수 있는 데이터를 제어` 라는 정의를 가지고 있습니다.

만약 시나몬이라는 사용자 (`id=1 name=시나몬 nickname=시나몬 address=가로수길 email=이메일`)가 물건을 구매한 내역을 저장한다고 가정합니다.

물건을 구매한 내역에는 아래의 데이터가 쌓이게 됩니다.

```
id=1 product=물건 buyer=시나몬 buyer_address=가로수길 buyer_email=이메일
id=2 product=물건2 buyer=시나몬 buyer_address=가로수길 buyer_email=이메일

...
```

현재는 2개의 필드가 있지만 만약 더 많은 상품을 구매했을 경우 `buyer=시나몬 buyer_address=가로수길 buyer_email=이메일` 이라는 데이터가 계속해서 중복되게 됩니다. 

현재 계정 데이터에는 위의 구매자 데이터에서 필요한 모든 데이터(이름, 주소, 이메일) 들어있기 때문에 **굳이 중복된 데이터를 또 넣어줄 필요가 없습니다.** 

해당 데이터값을 Foreign Key로 변경하면 아래와 같습니다.


```
id=1 product=물건 buyer_id=1
id=2 product=물건2 buyer_id=2

...
```

위처럼 변경하면 해당 구매자의 주소를 찾을 때 계정 테이블에서 해당 id값의 계정을 찾아 데이터를 불러오면 되기 때문에 훨씬 더 간단해집니다.

이처럼 다른 테이블을 참조하는 값이 Foreign Key이고, 위의 예제에서는 buyer_id가 Foreign Key가 됩니다.

<br/><br/>

### objects.get? objects.filter?

object.get과 object.filter는 모두 조건을 이용하여 해당 데이터를 가져오는 작업입니다.

`object.get`의 두가지 특징은 아래와 같습니다.

1. 하나의 데이터를 가져옵니다.
2. 만약 데이터가 없다면 에러를 일으킵니다

하지만 만약 2개 이상의 데이터가 있다면 `object.filter` 를 이용합니다.

1. 여러개의 데이터값이 배열로 리턴된다.
2. 만약 데이터가 없으면 빈값을 리턴한다.

이 외에도 다양한 명령어는 [Django QuerySet](https://docs.djangoproject.com/ko/2.1/ref/models/querysets/)을 참고하시면 됩니다.

<br/><br/>

### lte? get?

조건 키워드 중 하나입니다.

- lte : 작거나 같은 것
- gte : 크거나 같은 것

더 많은 조건 키워드는 [Django 조건 키워드](http://brownbears.tistory.com/63)를 참고하시면 됩니다.

<br/><br/>

## 심화

혹시 오늘 수업이 너무 쉬웠던 분들을 위해서 제가 Django Girls Tutorial을 진행하면서 공부했던 내용을 정리해보도록 하겠습니다!

참고로만 봐주시면 감사하겠습니다!

<br/>

### CSRF Token?

[참고 - CSRF Token이란?](https://itstory.tk/entry/CSRF-%EA%B3%B5%EA%B2%A9%EC%9D%B4%EB%9E%80-%EA%B7%B8%EB%A6%AC%EA%B3%A0-CSRF-%EB%B0%A9%EC%96%B4-%EB%B0%A9%EB%B2%95)

웹 어플리케이션 취약점 중 하나로 인터넷 사용자(희생자)가 자신의 의지와는 무관하게 공격자가 의도한 행위(수정, 삭제, 등록 등)를 특정 웹사이트에 요청하게 만드는 공격입니다.

즉 POST를 실행할 때 (데이터를 수정하거나 입력할 때), 사용자가 의도하지 않은 데이터를 넣어 (예를 들어 Facebook이라면 자신의 피드에 광고성 포스트가 뜨도록 한다.) 실행을 시켜 공격을 하는 방법입니다.

이를 방어하기 위하여, 사용자의 세션에 임의의 난수 값을 저장하고 사용자의 요청 마다 해당 난수 값을 포함 시켜 전송시킵니다(CSRF Token). 이후 Back-end 단에서 요청을 받을 때마다 세션에 저장된 토큰 값과 요청 파라미터에 전달되는 토큰 값이 일치하는 지 검증하여 해당 공격을 방어하는 방법입니다. 

<br/><br/>

### TIMEZONE 

프로젝트의 settings.py에 보면 TIMEZONE을 설정할 수 있습니다.

```python
LANGUAGE_CODE = 'ko-kr'

TIME_ZONE = 'Asia/Seoul'

USE_TZ = True
```

위의 한글과 TIMEZONE을 서울로 바꾸었다면 위와 같이 Setting이 되어있을 것입니다.

혹시 model을 생성하고 `created_date` 를 유심히 살펴보셨다면, 해당 필드에 created_date는 `UTC를 기준` 으로 데이터가 들어간 것을 보실 수 있습니다.

확인 방법은 아래와 같습니다.

`$ python manage.py shell` : 이 프로젝트를 이용하여 명령어를 입력해볼 수 있는 shell script가 뜹니다.

`>> from blog.models import Post` : Post 모델을 가져옵니다. 

`>> Post.objects.get(id=1).created_date` : 현재 Post 모델에 데이터 값이 하나라도 있다는 가정하에, id가 1인 값을 가져오고 created_date를 출력합니다.

그럼 해당 값의 **tzinfo** 가 **UTC**로 들어가 있는 것을 보실 수 있습니다.

하지만 **admin에서는 Asia/Seoul로 변경** 이 되어있고 **created_date를 웹에 출력했을 때도 Asia/Seoul** 로 되어있습니다.

<br/>

이는 Django에서 각 **세계의 시간을 편리하게 설정** 할 수 있게 하기 위하여 **model에는 UTC** 를 그리고 불러올 때는 **settings.py에 있는 TIMEZONE** 을 적용하여 데이터를 불러도록 하였습니다.

> 만약 현재 한국의 시간으로 model의 컬럼을 생성하였을 때, 미국에 맞게 변경을 하려면 해당 컬럼을 직접 변경하거나, 컬럼을 가져올 때 마다 변경을 해야합니다. 

하지만 Django에서는 UTC의 값을 읽고 settings.py에 있는 TIME_ZONE의 값으로 시간을 자동으로 변경하여 출력해줍니다.

만약 model에 부득이하게 한국 시간을 넣어야 할 경우 여러 가지 방법으로 변경할 수 있습니다.

<br/>

1. timezone.now가 아닌 timezone.localtime으로 변경하기

```python
from django.utils import timezone 
timezone.localtime()
```

<br/>

2. USE_TZ를 False로 변경하기

USE_TZ을 False로 변경하게되면 timezone을 사용하지 않고, 현재 자신의 서버 시간을 읽어옵니다.

```python
USE_TZ = False
```

<br/>

추가로 **datetime** 의 경우에는 `현재 서버의 시간` 을 읽어오는 데 이는 **naive datetime** 이라고 해서 timezone을 신경쓰지 않고 시간을 반환합니다. 

하지만 역시 datetime의 경우에도 모델에 저장할 때에는 **time-zone-aware datetime** 으로 UTC의 시간으로 저장됩니다.

<br/><br/>

### blank? Null?

- Null : **DB** 와 관련이 있으며, 주어진 **데이터베이스 컬럼** 이 **null 값** 을 가질 것인지 아닌지를 정의합니다.
- Blank : 유효성과 관련되어 있다. form.is_valid()가 호출될 때 **폼 유효성 검사** 에 사용됩니다.

<br/>

#### +)  예를 들어 null=True,  blank=False 옵션은

- null=True : **DB 레벨** 에서는 해당 필드가 NULL 될 수 있음을 의미합니다.
- blank=Fals : **Application 레벨** 에서는 해당 컬럼 값이 꼭 있어야하는 required 필드를 의미합니다. 

<br/>

#### 주의해야할 점

**CharField, TextField와 같은 문자열 기반 필드에 null=True를 정의하면 안됩니다.**

이는 `데이터 없음` 에 대한 두가지 값 (`None`, `빈문자열`)을 갖게 되기 때문에 이는 중복을 야기합니다.

또한 Null이 아닌 빈문자열을 사용하는 것이 [Django Convention (장고 코딩 스타일)](https://docs.djangoproject.com/en/2.1/internals/contributing/writing-code/coding-style/) 입니다.
