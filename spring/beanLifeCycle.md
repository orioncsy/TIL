# Bean Life Cycle

## 스프링 컨테이너

### 과정

- 컨테이너 초기화
    - 빈 객체 생성, 초기화 및 의존 객체 주입
- 컨테이너 종료

### 생명 주기

- Application Context를 이용해 객체 생성하고 스프링 컨테이너 초기화
- getBean()을 통해 컨테이너에 있는 빈 사용
- close()를 통해 컨테이너 종료

## Bean 생명 주기

### 과정

- 객체 생성
    - 스프링 컨테이너가 초기화할 때, 빈 객체 생성
- 의존 설정
    - 의존 관계를 설정
- 초기화
    - 빈 객체가 지정한 메서드 사용
- 소멸
    - 빈 객체가 지정한 메서드 사용

### Bean 객체 초기화 & 소멸

- 빈 객체는 InitializingBean, DisposableBean 인터페이스 구현
- 객체를 초기화할 때 InitializingBean에 있는 afterPropertiesSet() 메서드를 통해 초기화
- 객체를 소멸할 때 DisposableBean에 있는 destroy() 메서드를 통해 소멸

## Reference

[https://dongmin1994.tistory.com/15](https://dongmin1994.tistory.com/15)