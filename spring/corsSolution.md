# CORS

## 개념

### Origin

- URL(protocol, host, port, path, query string, fragment)에서 protocol, host, port까지가 origin에 해당

### SOP(Same Origin Policy)

- 같은 출처 정책으로 다른 출처로의 리소스 요청을 제한하는 보안 정책

### CORS(Cross Origin Resource Sharing)

- 다른 출처로의 요청을 예외적으로 허용하는 정책

## CORS Issue를 해결하는 방법

### CorsFilter 생성

- @Component를 붙이고 Filter 인터페이스를 구현하는 클래스 생성
- doFilter 메서드를 오버라이딩하고 내용 수정
    - 파라미터로 들어오는 ServletRequest, ServletResponse 객체를 HttpServletRequest, HttpServletResponse로 형변환
    - setHeader 메서드로 Access-Control-Allow-Origin, Access-Control-Allow-Method, Access-Control-Allow-Credentials 등을 수정

### Cross Origin annotation

- @CrossOrigin 을 컨트롤러에 붙여서 처리

### WebMvcConfigurer

- WebMvcConfigurer 객체를 생성하고 @Bean을 통해 등록한다.
- addCorsMappings 메서드를 오버라이딩하여 파라미터롤 들어오는 CorsRestry 객체를 가공처리하여 cors 대응

## Reference

[https://wonit.tistory.com/572](https://wonit.tistory.com/572)