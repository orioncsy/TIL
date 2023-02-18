# CORS

## 개념

### Origin

- Protocol(Scheme), domain, port를 합친 부분
- URL
    - [http://bookvillage.kro.kr:80/path/to/myfile.html?name=hgd&address=seoul](http://bookvillage.kro.kr/path/to/myfile.html?name=hgd&address=seoul)
    - [http://는](http://xn--sh1b/) scheme 즉 프로토콜에 해당한다.
    - bookvillage.kro.kr는 도메인에 해당한다.
    - :80는 포트번호에 해당한다.
    - /path/to/myfile.html는 path 즉 파일 경로이다.
    - ?name=hgd&address=seoul는 파라미터에 해당한다.
    - 이 중에서 프로토콜, 도메인, 포트번호([http://bookvillage.kro.kr:80](http://bookvillage.kro.kr/))를 합쳐 origin이라고 부른다.

### SOP & CORS

- SOP(Same Origin Policy)
    - 다른 origin으로 요청을 보낼 수 없도록 금지하는 브라우저 기본 보안 정책이다.
    - 예외
        - RFC 6454에서 <script> 태그로 javaScript를 실행하는 경우
        - <link> 태그로 스타일 시트 불러오는 경우
        - HTML 문서를 화면에 보여주는 경우
        - CORS 정책을 지키는 요청
    - CSRF 같은 공격을 방지하기 위한 것이다.
        - 브라우저에서 로그인한 사용자에게 해커가 다른 링크를 누르도록 유도하여 인증 정보를 담아서 해커가 작성한 javascript를 코드를 실행하도록 하는 공격
- CORS(Cross Origin Resource Sharing)
    - 다른 Origin의 요청도 처리할 수 있도록 하는 브라우저 정책

## CORS 동작 원리

### 기본 동작

- 브라우저가 헤더에 있는 origin에 자신의 origin을 담아서 요청을 보낸다.
- 서버가 요청을 받아 응답 헤더 중 Access-Controll-Allow-Origin에 허용하는 origin 목록을 담아서 보낸다.
- 브라우저가 응답 헤더 Access-Controll-Allow-Origin에서 요청 Origin이 있는지 검사한다.
- Access-Controll-Allow-Origin에 와일드카드(*)를 사용하면 모든 origin을 허용한다.

### Simple Request

- 특정 조건을 만족하는 경우에 preflight 요청 없이 한 번에 요청을 전송할 수 있다.
- 이름과는 달리 특정한 조건을 맞추기 까다롭다.
- 메서드가 GET, POST, HEAD 중 하나여야하고 User Agent가 자동으로 설정한 헤더를 제외하면 쓸 수 있는 헤더가 제한적이며 Content-type도 한정적이다.
- 동작 방식은 기본 동작과 같다.

### Preflight Request

- Simple Request의 조건에서 벗어난 요청의 경우 해당된다.
- 말 그대로 사전 요청을 보내고 안전한 origin인지 확인 후 요청을 보내는 방식
- 동작 방식
    - 클라이언트에서 메서드로 OPTIONS를 사용, Origin은 자신, Access-Control-Request-Method와 Access-Control-Request-Headers에 실제 요청에 사용할 메서드와 헤더를 작성해서 사전 요청을 보낸다.
    - 요청을 받은 서버가 Access-Control-Allow-Origin, Access-Control-Allow-Methods, Access-Control-Allow-Headers, Access-Control-Max-Age에 허용되는 origin, method, header, 사전 요청을 캐싱할 시간을 설정하여 응답한다.
    - 클라이언트에서 확인 후 실제 요청을 보낸다.

### Credentialed Request

- 요청할 때 쿠키나 Authorization 헤더에 토큰 값 등 인증 정보가 포함될 때 별도로 따라야 하는 요청
- XMLHttpRequest, jQuery의 ajax나 axios를 사용하면 withCredentials를 true로 설정
- fetch API를 사용하면 credentials 옵션을 include로 설정
- 서버는 Access-Control-Allow-Origin에 와일드 카드(*)가 아닌 origin을 설정해야 하고 Access-Control-Allow-Credentials를 true로 설정해야 한다.

## Reference

[[Web] CORS (Cross Origin Resource Sharing) 이해하기](https://it-eldorado.tistory.com/163)