# Filter & Interceptor

## Filter

### 개념

- J2EE 표준 기능으로 디스패처 서블릿에 요청이 전달되기 전후에 url 패턴에 맞는 모든 요청에 대한 부가작업
- 디스패터 서블릿은 스프링의 앞단 위치한 프론트 컨트롤러로 필터는 스프링 범위 밖에서 처리되는 것
- 톰캣과 같은 웹 컨테이너에 의해 관리되고 스프링 빈으로 등록은 된다.

### 사용

- javax.servlet의 Filter 인터페이스를 구현하여 사용 가능
- 3가지 메서드 포함
- init
    - 필터 객체를 초기화하고 서비스에 추가하기 위한 메서드
    - 웹 컨테이너가 1회 실행
- doFilter
    - url pattern에 맞는 모든 http 요청이 디스패처 서블릿에 도달하기 전 웹 컨테이너에 의해 실행되는 메서드
    - 파라미터로 FilterChain이 존재하는데 chain.doFilter를 통해 다음 대상으로 요청 전달 가능
    - chain.doFilter 전후로 필요한 작업 실행 가능
- destroy
    - 필터 객체를 서비스에서 제거하고 사용하는 자원을 반환하는 메서드
    - 웹 컨테이너에 의해 1번 호출된다.

## Interceptor

### 개념

- Spring에서 제공하는 기술로 디스패처 서블릿이 컨트롤러를 호출하기 전후에 요청과 응답을 가공할 수 있는 기능
- 웹 컨테이너에서 관리되는 filter와 달리 interceptor는 spring context에서 동작
- 디스패처 서블릿은 핸들러 매핑을 통해 적절한 컨트롤러를 찾도록 요청하는데 그 결과로 HandlerExecutionChain을 돌려준다.
- 이 체인에 1개 이상의 인터셉터가 포함된다면 순차적으로 거치고 컨트롤러를 실행
- 필터를 거쳐 디스패처 서블릿이 요청을 받은 이후에 동작한다.

### 사용

- org.springframework.web.servlet의 HandlerInterceptor 인터페이스를 구현
- 3가지 메서드 존재
- preHandle
    - 컨트롤러가 호출되기 전 실행
    - 3번째 파라미터는 handler로 핸들러 매핑이 찾아준 컨트롤러 빈에 매핑되는 HandlerMethod라는 새로운 타입 객체로 @RequestMapping이 붙은 메서드 정보를 추상화한 것
    - 반환형이 boolean으로 true이면 다음 단계 진행, false이면 다음 단계 또는 컨트롤러 실행하지 않고 중단
- postHandle
    - 컨트롤러 호출 후에 실행
    - 컨트롤러가 반환하는 ModelAndView 타입 정보가 제공되는데, 최근에는 Json 형태로 데이터를 제공하는 RestAPI 기반 컨트롤러(@RestController)를 이용하기 때문에 자주 사용되지 않는다.
- afterCompletion
    - 모든 뷰에서 최종 결과를 생성하는 일을 포함해 모든 작업 완료 후 실행
    - 사용한 리소스를 반환할 때 사용
    - postHandle와 달리 컨트롤러 하위 계층에서 작업하다가 중간에 예외가 발생하더라도 반드시 호출된다.

### AOP와 비교

- 인터셉터 대신 컨트롤러에 부가기능을 어드바이스를 만들어 AOP를 적용 가능
- 그러나 컨트롤러 호출과정에 적용되는 부가 기능은 인터셉터를 사용하는 것이 편의
    - 컨트롤러는 타입과 실행 메서드가 제각각이라 포인트컷 작성이 어려움
    - 컨트롤러는 파라미터나 리턴 값이 일정하지 않다.
    - AOP와 달리 인터셉터에서는 파라미터로 HttpServletRequest나 HttpServletResponse가 넘어온다.

## Filter와 Interceptor의 차이

### Request/Response 조작 여부

- 필터는 doFilter 메서드를 통해 다음 필터를 호출할 때 Request와 Response를 넘겨주기 때문에 다른 객체를 넘겨줄 수 있다.
- 인터셉터의 경우 boolean 형태로 다음 인터셉터나 컨트롤러가 실행되거나 중단되기 때문에 Request/Response를 조작할 수 없다.

### 사용 용도

- 필터
    - 스프링과 무관하게 전역적으로 처리해야 하는 작업들
    - 공통적인 보안 작업으로 올바른 요청인지 확인 가능
    - 모든 요청에 대한 로깅 또는 검사
    - 이미지 데이터 압축 및 문자열 인코딩과 같은 웹 앱 전반적으로 사용되는 기능
    - Spring과 분리되어야 하는 기능
    - 대표적으로 spring security에서 filter를 사용
        - spring mvc와 종속적이지 않고 인가/인증을 처리 가능
- 인터셉터
    - 클라이언트 요청과 관련되어 전역적으로 처리해야 할 작업들
    - 세부적으로 적용해야 하는 인증/인가
        - 특정 그룹의 사용자가 어떤 기능을 사용하지 못하게 컨트롤러가 넘어가기 전에 검사
    - API 호출에 대한 로깅 또는 검사
    - Controller로 넘겨주는 정보 가공
        - HttpServletRequst/Response를 전달받기 때문에 객체 자체를 조작할 수 없지만 내부적인 값을 변경 가능하기 때문에 컨트롤러에게 넘어가는 정보를 가공 가능

## Reference

[https://mangkyu.tistory.com/173](https://mangkyu.tistory.com/173)