# Controller

## @controller

### View 반환

- 전통적인 Spring MVC로 view를 반환한다.

### 과정

- Client는 URI 형식으로 웹 서비스에 요청
- DispatcherServlet이 요청을 위임할 handler를 찾기 위해 HandlerMapping에 요청
- HandlerAdapter를 통해 controller에게 위임
- Controller는 ViewName을 반환
- DispatcherServlet은 ViewResolver를 통해 ViewName에 해당하는 view를 찾아 Client에게 반환

### Data 반환

- 데이터를 반환하기 위해서 @ResponseBody를 사용
- 이것을 통해 Controller도 Json 형태의 데이터를 반환 가능

### 과정

- Client는 URI 형식으로 웹 서비스에 요청
- DispatcherServlet이 요청을 위임할 handler를 찾기 위해 HandlerMapping에 요청
- HandlerAdapter를 통해 controller에게 위임
- Controller는 요청 처리 후 객체를 반환(ResponseEntity라는 객체에 담아 반환)
- 객체를 반환하기 위해 ViewResolver가 아닌 HttpMessageConverter 동작
    - HandlerAdapter와 controller가 요청을 주고받을 때 메시지컨버터 사용
- 반환되는 객체는 Json 형태로 직렬화 되어 사용자에게 반환(@ResponseBody를 사용)

## @RestController

### 개념

- @Controller에서 @ResponseBody가 추가된 것
- Json 형태의 객체로 데이터를 반환

### 과정

- Client는 URI 형식으로 웹 서비스에 요청
- DispatcherServlet이 요청을 위임할 handler를 찾기 위해 HandlerMapping에 요청
- HandlerAdapter를 통해 Controller에게 위임
- Controller는 요청 처리 후 객체를 반환(ResponseEntity라는 객체에 담아 반환)
- 객체를 반환하기 위해 ViewResolver가 아닌 HttpMessageConverter 동작
    - HandlerAdapter와 controller가 요청을 주고받을 때 메세지컨버터 사용
- 반환되는 객체는 Json 형태로 직렬화되어 사용자에게 반환(@ResponseBody 필요가 없음)

## Reference

[https://mangkyu.tistory.com/49](https://mangkyu.tistory.com/49)