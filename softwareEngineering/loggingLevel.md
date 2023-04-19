# Logging level

## 개념

### logging level

- log4j 라이브러리를 사용하여 구현
- ERROR, WARN, INFO, DEBUG로 구분되어 작성

## 종류

### ERROR

- 에러 로그는 프로그램에 큰 문제가 발생
- 즉시 조치를 취해야 한다.
- db 사용 불가나 중요 에러 발생

### WARN

- 주의해야 하는 상태지만 프로세스는 지속적으로 작동
- 종료가 발생하는 부분
    - 명확한 문제 - 캐시값 사용, 데이터 사용 불가
    - 잠재적 문제 - 개발 모드로 프로그램 시작, 관리자 콘솔 비밀번호가 보호되지 않고 접속

### INFO

- 중요한 비즈니스 프로세스의 시작과 종료를 알림

### DEBUG

- 개발자가 기록할 만한 가치가 있는 정보를 남기는 레벨

## Reference

[https://gyoogle.dev/blog/web-knowledge/Logging%20Level.html](https://gyoogle.dev/blog/web-knowledge/Logging%20Level.html)