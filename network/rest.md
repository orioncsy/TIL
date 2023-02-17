# Rest

## 개념

### 정의

- REpresentational State Transfer
- 자원의 표현으로 자원의 상태를 전달하는 것
    - 자원 : 소프트웨어가 관리하는 모든 것
    - 자원의 표현 : 자원을 표현하기 위한 이름
    - 자원의 상태 전달 : 데이터가 요청되는 시점의 자원의 상태를 전달
- 웹의 기존 기술과 http프로토콜을 사용하여 웹의 장점을 살리는 아키텍처 스타일
- 네트워크 상 서버와 클라이언트 사의 통신 방식 중 하나

### 구체적인 의미

- HTTP URI를 통해 자원을 표시하고 HTTP Method(get, put, delete, post, patch)를 통해 자원에 대한 CRUD를 표현하는 방식

## 구성 요소

### 자원 URI

- 모든 자원에 고유한 ID가 존재하고 자원은 서버에 존재
- HTTP URI로 표현
- 클라이언트는 URI를 통해 자원을 지정하고 상태 처리를 서버에게 요청한다.

### 작업 HTTP method

- GET, POST, PUT, PATCH, DELETE, OPTION, HEAD, TRACE 등의 메서드를 사용

### 표현

- 하나의 자원은 JSON, XML 등을 통해 데이터를 주고받는다.

## 특징

### 서버-클라이언트 구조

- 자원을 가지고 있는 서버와 자원의 처리를 요청하는 클라이언트와 통신하는 구조

### Stateless

- HTTP 프로토콜을 기반으로 무상태성을 갖는다.

### Cacheable

- HTTP가 가지고 있는 캐싱 기능을 적용할 수 있다.

### Layered System

- 클라이언트는 rest api 서버만 호출한다.
- rest 서버는 다중 계층으로 구성 가능하다.
    - 보안, 로드밸런싱, 암호화, 인증 등을 사용 가능
- 프록시나 게이트웨이 등의 네트워크 중간 매체 사용 가능

### Code on demand

- 서버로부터 스크립트를 받아서 클라이언트에서 실행
- 선택적인 부분이다.

### Uniform Interface

- URI로 지정된 자원에 대한 조작을 통일된 인터페이스로 수행

## 장단점

### 장점

- HTTP 프로토콜을 사용하여 REST API를 위한 별도의 인프라 구축이 필요 없다.
- HTTP 프로토콜을 사용하는 모든 플랫폼에서 사용 가능

### 단점

- 사용할 수 있는 메서드 종류가 한정적이다.
- 구형 브라우저가 제대로 지원을 못해준다.

# REST API

## 개념

### Rest API

- API(Application Programming Interface)
    - 데이터와 기능을 가지고 컴퓨터 프로그래밍 간 정보 교환을 하는 것
- Rest API
    - API 설계를 Rest 기반으로 구현한 것
- 확장성과 재활용성이 뛰어나다.
- HTTP 표준을 기반으로 하기 때문에 그 기반으로 클라이언트, 서버를 구현할 수 있다.

## REST API 설계

### 기본 규칙

- URI는 정보의 자원을 표시
    - 동사보다 명사, 대문자보다 소문자 사용
    - document 이름은 단수명사, collection 이름과 store 이름은 복수 명사
- GET, POST, PUT, PATCH, DELETE, OPTION, HEAD, TRACE 등의 메서드를 사용

### 설계 규칙

- 슬래시(/)는 계층 관계에 사용
- URI 마지막에는 /를 사용하지 않는다.
- 불가피하게 긴 URI에는 하이픈(-)을 사용한다.
- 밑줄(_)은 사용하지 않는다.
- URI 경로는 소문자를 사용한다.
- URI에 확장자를 포함하지 않는다.

### 응답 상태 코드

- 1XX : 전송 프로토콜 수준의 정보 교환
- 2XX : 클라이언트 요청이 성공적으로 수행됨
- 3XX : 클라이언트 요청이 완료되기 위해 추가적인 행동을 취해야 함
- 4XX : 클라이언트의 잘못된 요청
- 5XX : 서버 쪽 오류

# RESTful

## 개념

### RESTful

- REST 아키텍처를 구현하는 웹 서비스를 나타내기 위한 용어
- 일관적인 컨벤션을 통한 API 이해도와 호환성을 높이기 위한 목적

## Reference

[[Network] REST란? REST API란? RESTful이란? - Heee's Development Blog](https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html)