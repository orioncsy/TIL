# Bean Scope

## 개념

### Bean Scope

- Bean이 존재할 수 있는 범위
- Bean으로 생성된 객체들은 스프링 컨테이너에서 종료될 때까지 스프링이 관리
- spring bean들은 singletone scope로 관리

## 종류

### Singletone

- Spring IoC Container 내부에 하나의 Bean에 대해 하나의 객체만 존재
- 모든 bean은 scope이 정의되어 있지 않으면 Singletone이다.
- 스프링 IoC container에서 단 한 번 생성되어 참조된다.

### Prototype

- 하나의 Bean 정의에 다수 객체 존재
- 모든 요청에 새로운 객체를 생성하여 주입
- stateful한 bean에는 prototype을 사용하고 stateless bean은 singletone을 사용

### Request

- 하나의 Bean 정의에 HTTP request 생명주기 안에 하나의 객체만 존재
- Web-aware Spring ApplicationContext 내에서만 유효

### Session

- 하나의 Bean 정의에 HTTP session 생명주기 안에 하나의 객체만 존재
- Web-aware Spring ApplicationContext 내에서만 유효

### Global Session

- 하나의 Bean 정의에 global HTTP request 생명주기 안에 하나의 객체만 존재
- Web-aware Spring ApplicationContext 내에서만 유효

### Application

- 하나의 Bean 정의에 Servlet Context 생명주기 안에 하나의 객체만 존재
- Web-aware Spring ApplicationContext 내에서만 유효

## Reference

[https://yamyam-spaghetti.tistory.com/56](https://yamyam-spaghetti.tistory.com/56)