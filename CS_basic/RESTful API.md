# RESTful API

Date Created: Apr 28, 2020 8:21 PM
tag: CS기초

# REST API의 구성

1. 자원(Resource) - URI
2. 행위(Verb) - HTTP Method
3. 표현(Representations)

# 대표적인 HTTP Method 4가지

- GET: 해당 리소스를 조회
- POST: 해당 리소스를 생성
- DELETE: 해당 리소스를 삭제
- PUT: 자원의 전체 교체, 자원의 모든 필드 필요
    - PATCH: 자원의 부분 교체, 자원 내 일부분만 필요

CRUD를 기반으로 만들어지는 Method 들

# URI Rules

1. 마지막에 /를 포함하지 않는다.
2. Underscore(_)대신 dash(-)를 사용한다.
3. 소문자를 사용한다.
4. 행위(method)는 URL에 포함하지 않는다.(명사 위주의 사용)
5. 컨트롤 자원을 의미하는 URL 예외적으로 동사를 허용한다.
    1. http://[api.test.com](http://api.test.com/)/posts/duplicating **BAD**
    2. http://[api.test.com](http://api.test.com/)/posts/duplicate **GOOD**
6. HTTP status code로 상태 에러를 나타낸다.

### REST(REpresentational State Transfer)는 왜 나왔는가?

- 통신 기술들이 어려워서 익숙한 web(HTTP)를 있는 그대로 적용 해 보려고
- 서버의 스펙(스타일) 같은 것
    - **해당 스펙의 흐름이 보이면 RESTful 하다고 함**
- HTTP 1.1의 흐름을 타고 급부상
    - HTTP 1.1 == HTTP 1.0(GET,POST) + (PUT, DELETE)
- URI를 자원으로 표현 하는 것