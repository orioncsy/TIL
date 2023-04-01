# Transaction Propagation

## 개념

### JPA 전파 단계

- 트랜잭션이 다른 트랜잭션을 실행할 경우 어떻게 처리하는지에 대한 개념

## 종류

### REQUIRED

- 기본 DEFAULT로 설정되어 진행중인 트랜잭션이 있다면 해당 트랜잭션을 사용하고 없으면 생성

### REQUIRES_NEW

- 항상 새로운 트랜잭션 생성
- 진행 중인 트랜잭션이 있는 경우 중지하고 새로운 트랜잭션을 생성하고 끝나면 기존 트랜잭션 실행

### SUPPORTS

- 트랜잭션을 필요하지 않는다.
- 기존 트랜잭션이 있다면 사용

### NOT_SUPPORTS

- 트랜잭션을 필요하지 않는다.
- 기존 트랜잭션이 있다면 중지하고 작업이 끝나면 기존 트랜잭션 다시 실행

### MANDATORY

- 트랜잭션이 항상 필요
- 실행 중인 트랜잭션이 없다면 예외 발생

### NEVER

- 트랜잭션이 항상 불필요
- 실행 중인 트랜잭션이 있다면 예외 발생

### NESTED

- 진행 중인 트랜잭션이 있다면 중첩된 트랜잭션을 실행

## Reference

[https://steady-hello.tistory.com/121](https://steady-hello.tistory.com/121)