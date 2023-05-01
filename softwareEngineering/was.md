# WAS & Web Server

## 개념

### Static Page

- 정적페이지는 바뀌지 않는 페이지를 의미
- 항상 동일한 페이지를 반환
- image, html, css 파일 등 컴퓨터에 저장되는 파일들
- 웹 서버가 파일 경로를 받아, 해당 파일 콘텐츠를 반환

### Dynamic Page

- 동적 페이지는 인자 값에 따라 바뀌는 페이지
- 인자의 내용에 따라 동적인 컨텐츠를 반환
- WAS를 통해 만들어지는 실행되는 프로그램에 의해 만들어진 결과물
    - Servlet이 대표적으로 WAS 위에서 구동되는 자바 프로그램이다.

## Web Server VS WAS

### Web Server

- 하드웨어 측면
    - Web Server를 구동하는 컴퓨터
- 소프트웨어 측면
    - 웹 클라이언트로부터 HTTP 요청을 받아 정적 콘텐츠를 제공하는 프로그램
- 기능
    - 정적 컨텐츠를 제공하거나 동적 컨텐츠를 제공하기 위해 WAS에 요청 전달
- 종류
    - Apache, nginx

### WAS

- DB 조회나 비즈니스 로직을 처리하여 동적 컨텐츠를 제공하는 애플리케이션 서버
- HTTP를 통해 애플리케이션을 수행해주는 미들웨어
- Web Container 혹은 Servlet Container
    - JSP나 Servlet을 실행시킬 수 있는 소프트웨어
- 기능
    - 프로그램 실행 환경 및 DB 접근 기능 제공
    - 여러 트랜잭션 관리
    - 업무 처리 비즈니스 로직 수행
- WAS 종류
    - Tomcat, JBoss

## Web Server와 WAS의 분리 목적

### Web Server 목적

- 정적 컨텐츠만 처리하도록 기능을 분리시켜 WAS의 부담을 줄인다.

### WAS 목적

- 요청에 따라 DB에서 데이터를 가져와 로직을 동적으로 수행하고 결과물을 제공
- WAS에서 Web Server 역할까지 담당하면 부하가 커지기 때문에 분리한다.

## Web Service Architecture

### 클라이언트

- HTTP 요청을 받는다.

### Web Server

- 클라이언트의 요청을 받아서 WAS에 전달

### WAS

- 관련 servlet을 메모리에 적재
- web.xml을 참조해 Servlet에 대한 스레드 생성
- HttpServletRequest, HttpServletResponse 객체를 생성해 servlet에 전달
- 스레드는 servlet의 service() 메서드를 실행
- service() 메서드는 doGet(), doPost() 메서드 호출하고 적절한 동적 페이지를 response에 담아 WAS에 전달
- Response 객체를 HttpResponse로 변환하여 Web server에 전달
- 스레드를 종료하고 HttpServletRequest,HttpServletResponse 객체 제거

## Reference

[https://gyoogle.dev/blog/web-knowledge/Web%20Server%EC%99%80%20WAS%EC%9D%98%20%EC%B0%A8%EC%9D%B4.html](https://gyoogle.dev/blog/web-knowledge/Web%20Server%EC%99%80%20WAS%EC%9D%98%20%EC%B0%A8%EC%9D%B4.html)