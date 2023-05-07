# Dirty Checking

## 개념

### Dirty checking

- 트랜잭션 내에서 Entity에 변경 사항이 일어났을 때 자동으로 DB에 반영

## 작동 원리

### JPA dirty checking

- JPA에서는 트랜잭션 내에서 Entity에 변경 사항이 일어났을 때 자동으로 update 쿼리를 날려 반영

### 동작 방식

- JPA에서 트랜잭션이 실행
- Entity를 조회
- 조회된 Entity의 스냅샷 저장
- Entity의 데이터 변경
- 트랜잭션 커밋 후 스냅샷과 현재 Entity를 비교
- 변경 사항을 update 쿼리로 구성 및 실행

## 특징

### 실행 대상

- dirty checking 검사 대상은 영속성 컨텍스트에 저장된 Entity
- 준영속, 비영속 Entity는 DB에 반영되지 않는다.

### @DynamicUpdate

- dirty checking은 변경된 Entity의 모든 내용을 update 쿼리에 담는다.
- Entity에 많은 필드가 존재하는 경우 비효율적일 수 있다.
- @DynamicUpdate를 사용하면 변경된 필드만 update할 수 있다.

## Reference

[https://gyoogle.dev/blog/web-knowledge/spring-knowledge/%5BSpring%20Data%20JPA%5D%20Dirty%20Checking.html](https://gyoogle.dev/blog/web-knowledge/spring-knowledge/%5BSpring%20Data%20JPA%5D%20Dirty%20Checking.html)