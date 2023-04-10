# Stored Procedure

## 개념

### Stored Procedure(저장 프로시저)

- 일련의 쿼리를 하나의 함수처럼 사용하도록 모아놓은 집합
- 원하는 데이터를 가져오기 위해 여러 query를 날려야 하는 경우에 사용
- 여러 상황에서 인자 값만 전달하면 원하는 데이터를 가져올 수 있다.

## 사용

### 프로시저 생성

- CREATE OR REPLACE PROCEDURE 프로시저명(변수명 IN 데이터 타입, 변수명 OUT 데이터 타입) IS 변수명 데이터 타입 … BEGIN 로직 작성 END;
- IN의 경우 인자 값으로 전달하는 경우이고 OUT은 해당 값에 값을 대입하는 처리를 할 경우 사용

### 프로시저 호출

- EXEC 프로시저명(전달 인자);

## 장단점

### 장점

- 최적화 및 캐시
    - 프로시저 최초 실행 시 최적화로 컴파일되고 프로시저 캐시에 저장
    - 프로시저가 이후에 호출될 때 다시 컴파일하지 않고 캐시에서 가져와 사용
- 유지 보수
    - 프로시저 내부만 변경하여 다른 작업으로 변경 가능
- 트래픽 감소
    - 클라이언트가 sql문을 직접 작성하지 않고 프로시저명에 인자만 전달하면 되기 때문에 서버와 클라이언트 사이의 트래픽이 적다.
- 보안
    - 프로시저 내 참조 중인 테이블 접근을 막을 수 있다.

### 단점

- 호환성
    - 구문 규칙이 sql과 psm 표준과 호환성이 낮다.
    - PSM - sql에 대해 절차적 로직을 실행하는 방법을 제공하는 절차적 언어
    - Stored procedure는 psm 코드로 서버에 저장
- 성능
    - 문자나 숫자에서 C나 Java보다 느리다.
- 디버깅
    - 에러가 발생했을 때 디버깅이 어렵다.

## Reference

[https://gyoogle.dev/blog/computer-science/data-base/Stored%20PROCEDURE.html](https://gyoogle.dev/blog/computer-science/data-base/Stored%20PROCEDURE.html)