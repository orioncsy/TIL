# HTTP Status Code

## 개념

### HTTP status code

- http api를 통해 통신할 때 응답 상태 코드를 통해 통신 성공을 확인할 수 있다.

### 기본적인 상태 코드

- 100번대 : 정보 확인
- 200번대 : 통신 성공
- 300번대 : 통신 완료를 위한 추가적인 작업 필요
- 400번대 : 클라이언트 오류
- 500번대 : 서버 오류

## 주요 상태 코드

### 200번대

- 200 OK - 요청 성공(GET)
- 201 Create - 생성 성공(POST)
- 202 Accepted - 요청 접수는 하지만 리소스 처리는 하지 않는다.
- 204 No Contents - 요청 성공이지만 내용이 없다.

### 300번대

- 300 Multiple Choice - 요청 URI에 여러 리소스가 존재
- 301 Move Permanently - 요청 URI가 새로운 위치로 이동
- 304 Not Modified - 요청 URI의 내용이 변경되지 않음

### 400번대

- 400 Bad Request - 정의되지 않은 API 요청
- 401 Unauthorized - 인증 오류
- 403 Forbidden - 권한 밖의 시도
- 404 Not Found - 요청 URI에 리소스가 존재하지 않음
- 405 Method Not Allowed - 정의되지 않은 메서드 호출
- 406 Not Acceptable - 처리 불가
- 408 Request Timeout - 요청 대기 시간 초과
- 409 Conflict - 모순
- 429 Too Many Request - 요청 횟수 상한 초과

### 500번대

- 500 Internal Server Error - 서버 내부 오류
- 502 Bad Gateway - 게이트웨이 오류
- 503 Service Unavailable - 서비스 이용 불가
- 504 Gateway timeout - 게이트웨이 시간 초과

## Reference

[https://gyoogle.dev/blog/web-knowledge/HTTP%20status%20code.html](https://gyoogle.dev/blog/web-knowledge/HTTP%20status%20code.html)