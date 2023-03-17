# Spring & Spring Boot

## Spring

### 개념

- 자바 애플리케이션을 빌드할 수 있는 오픈 소스 프레임워크
- Struts, JSP, Hibernate 등의 다양한 프레임워크에 대한 지원

### Spring Triangle

- IoC
    - 객체를 생성, 생명주기에 제어권이 바뀜
    - POJO(Plain Old Java Object) - 자바 모델, 기능, 프레임워크를 따르지 않는 java Object를 지칭하며 대표적으로 자바 Bean을 의미
    - Pojo의 생성, 초기화, 서비스, 소멸에 대한 권한을 가짐
    - IoC는 객체의 생성을 책임지고 의존성을 관리함
    - DI라는 의존성 주입을 통해 클래스 간 의존 관계를 빈 설정을 기반으로 컨테이너가 자동 연결
- AOP(Aspect Oriented Programming)
    - 주요 기능과 부가 기능을 분리하여 관점별로 개발하는 방식
    - 기존 코드의 메서드 전후에 필요한 로직 수행
    - @Transactional이 AOP를 기반으로 만들어졌다.
    - aspect(부가 기능들을 모듈화), target(부가 기능을 수행해줘야 하는 클래스나 메서드 대상), advice(순수하게 부가 기능만 구현된 구현체), joinPoint(advice를 실제 수행할 시점), PointCut(부가 기능 수행할 시점에 대한 스펙 정의서), advisor(PointCut과 advice를 지칭)
- PSA(Portable Service Abstraction)
    - 다른 여러 모듈을 사용할 때 별도의 추상화 레이어 제공
    - Spring web mvc, spring Transaction, Spring Cache 등이 해당
    - 추상화 계층을 사용해서 어떤 기술을 내부에 숨기고 개발자에게 편의성을 제공
    - 기본적으로 톰캣을 사용하는데 dependency에서 webflux로 바꾸고 실행하면 netty 기반으로 돌아가는 것이 대표적인 예

## Spring Boot

### 개념

- 기존의 spring 프레임워크 위에 구축
- 스프링 프레임 워크를 사용하기 위한 많은 설정 부분을 자동화하여 사용자가 편하게 스프링 프레임워크를 사용할 수 있다.

## 차이점

### Dependency

- Spring은 dependency를 추가할 때 설정 파일이 길고 버전도 하나하나 관리해야 한다.
- Spring Boot에서는 build.gradle 파일에 dependency를 간단하게 추가하고 관리 가능

### Configuration

- Spring은 configuration을 설정할 때 모든 애노테이션과 빈을 등록해줘야 한다.
- Spring Boot에서는 build.gradle에 간단하게 추가하여 등록 가능
- Spring Boot는 AutoConfiguration 사용 가능
    - @SpringBootApplication이라는 애노테이션 사용 가능
    - @ComponentScan, @EnableAutoConfiguration을 통해 빈을 등록해 주고 외부 라이브러리, 내장 톰캣 등을 사용 가능

### 배포

- Spring에서는 war 파일을 WAS에 담아서 배포
- Spring boot는 내장 tomcat이 있기 때문에 jar 파일로 간편하게 배포가 가능

## Reference

[https://yamyam-spaghetti.tistory.com/56](https://yamyam-spaghetti.tistory.com/56)

[https://velog.io/@edenko/스프링의-핵심-3대-요소-Spring-Triangle](https://velog.io/@edenko/%EC%8A%A4%ED%94%84%EB%A7%81%EC%9D%98-%ED%95%B5%EC%8B%AC-3%EB%8C%80-%EC%9A%94%EC%86%8C-Spring-Triangle)