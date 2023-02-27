# Transaction

## 개념

### Transaction

- 데이터 베이스의 상태를 변화시키기 위한 최소한의 작업 단위

## ACID

### Atomicity

- 작업 단위가 모두 성공하거나 실패하도록 하는 특성

### Consistency

- 작업을 처리하기 전후의 상태를 일관되게 유지

### Isolation

- 개별 트랜잭션이 서로에게 영향을 주지 않는 특성

### Durability

- 트랜잭션 결과를 데이터베이스에 영구적으로 저장

## 상태

### Active

- 트랜잭션이 활동 상태, 실행 중 상태

### Failed

- 트랜잭션 실패, 트랜잭션이 더 이상 진행할 수 없는 상태

### Partially committed

- commit 되기 전의 sql문이 실행 완료된 상태

### committed

- 트랜잭션 완료 상태

### Aborted

- 트랜잭션 취소 상태, 실행 이전으로 돌아간다.

## 유의점

### 트랜잭션 사용 유의점

- 트랜잭션의 범위를 최소화해야 한다.
- 데이터 베이스 커넥션은 제한적이라 사용 가능한 커넥션 수가 줄어들 수 있다.

### deadlock

- 복수의 트랜잭션을 사용하는 경우 두 개 이상의 트랜잭션이 자원을 소유한 채 다른 트랜잭션과 서로 자원을 요구하는 상태

### 교착 상태의 빈도를 낮추는 방법

- 트랜잭션을 자주 커밋
- 정해진 순서로 테이블 접근
- 읽기 잠금 획득 사용을 절제
- 테이블 단위의 잠금을 획득해 갱신을 직렬화하면 동시성이 떨어지지만 교착상태 회피

## 구현

### 트랜잭션 동기화

- jdbc 사용 상의 동기화 작업

```
TransactionSynchronizeManager.initSynchronization();
Connection conn = DataSourceUtils.getConnection(dataSource);
// 작업DataSourceUtils.releaseConnection(conn, dataSource);
TransactionSynchronizeManager.unbindResource(dataSource);
TransactionSynchronizeManager.clearSynchronization();

```

- 동기화 작업을 통해 구현
- hibernate에서는 session을 사용하며 기술의 종속성 문제 발생

### 트랜잭션 추상화

- PlatformTransactionManager라는 인터페이스 활용

```
TransactionStatus status = this.transactionManager.getTransaction(new DefaultTransactionDefinition());

	try {
		Object result= invoation.proceed();
		this.transactionManager.commit(status);
		return result;
	} catch (Exception e) {
		this.transactionManager.rollback(status);
		throw e;
	}

```

### AOP 사용으로 트랜잭션 분리

- @Transactional 애너테이션으로 처리

## 트랜잭션 세부 설정

### 트랜잭션 전파

- 트랜잭션 내부에서 또 다른 트랜잭션을 요청하였을 때 처리 방식
- PROPAGATION_REQUIRED
    - 새로 요청된 트랜잭션을 기존 트랜잭션에 참여시켜서 처리
- PROPAGATION_REQUIRES_NEW
    - 독자적인 트랜잭션을 생성해서 처리
- PROPAGATION_NOT_SUPPORTED
    - 새로 요청한 트랜잭션을 트랜잭션 처리하지 않는 방식

### 격리 수준

- 여러 트랜잭션이 실행될 때 격리를 하는 수준
- 위에서부터 독립성이 크고 성능이 떨어진다.
- READ UNCOMMITTED
    - 다른 트랜잭션이 commit, rollback 상관없이 데이터 조회
- READ COMMITTED
    - 다른 트랜잭션이 commit 되어야만 read
    - oracle 기본
- REPEATABLE READ
    - 트랜잭션이 시작되기 전 commit 된 데이터만 read
    - MySQL 기본
- SERIALIZABLE
    - 가장 단순한 격리 수준
    - 읽기 작업에도 공유 잠금을 설정해 동시에 다른 트랜잭션에서 레코드 변경

### 제한 시간

- 트랜잭션을 실행하는 제한 시간 설정 가능
- 트랜잭션 전파 중에 트랜잭션을 직접 시작하는 경우 작동 가능

### 읽기 전용

- 트랜잭션 내 데이터의 조작을 차단

## Reference

[Interview_Question_for_Beginner/Database at master · JaeYeopHan/Interview_Question_for_Beginner](https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/Database#transaction)

[[Spring] 트랜잭션에 대한 이해와 Spring이 제공하는 Transaction(트랜잭션) 핵심 기술 - (1/3)](https://mangkyu.tistory.com/154)

[[db] 트랜잭션 격리 수준(isolation level)](https://joont92.github.io/db/%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98-%EA%B2%A9%EB%A6%AC-%EC%88%98%EC%A4%80-isolation-level/)