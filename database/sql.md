# SQL

## DML(Data Manipulation Language)

### 개념

- 데이터베이스의 데이터를 관리하는 데 사용
- 자동으로 커밋되지 않아 롤백할 수 있다.
- 실제 테이블에 영향을 주기 위해서는 커밋을 해야 한다.

### 종류

- SELECT
    - 데이터 조회
- INSERT
    - 데이터 삽입
- UPDATE
    - 데이터 수정
- DELETE
    - 데이터 삭제
    - 테이블에 있는 모든 데이터를 삭제할 경우 TRUNCATE 사용 권고
    - 삭제된 데이터의 로그를 TRUNCATE에서는 저장하지 않아 시스템 부하가 적지만 롤백이 불가
- MERGE
    - 데이터가 테이블에 존재하지 않으면 INSERT, 존재하면 UPDATE
- CALL
    - PL/SQL 또는 JAVA 서브 프로그램 호출
- EXPLAIN PLAN
    - 데이터 접근 경로 해석
- LOCK TABLE
    - 동시성 제어

## DDL(Data Definition Language)

### 개념

- 데이터 베이스 구조, 스키마를 변경할 때 사용
- 명령어를 입력하는 순간 자동으로 커밋된다.

### 종류

- CREATE
    - 테이블 생성
- ALTER
    - 테이블 구조 변경
- DROP
    - 테이블의 구조와 데이터 모두 삭제
- RENAME
    - 테이블 이름 변경
- COMMENT
    - 데이터 주석 추가
- TRUNCATE
    - 테이블 구조는 남기고 모든 데이터 삭제

## DCL(Data Control Language)

### 개념

- 데이터 베이스에 권한 부여
- 명령어를 입력하는 순간 자동 커밋된다.

### 종류

- GRANT
    - 데이터베이스에 대한 사용자 액세스 권한 부여
- REVOKE
    - GRANT로 부여된 권한 회수

## TCL(Transaction Control Language)

### 개념

- 데이터 보안, 무결성, 회복, 병행, 수행제어 등 정의에 사용

### 종류

- COMMIT
    - 트랜잭션 결과 저장 반영
- ROLLBACK
    - 데이터베이스를 마지막 COMMIT 시점으로 복귀
- SAVEPOINT
    - 롤백할 때 복귀 되는 현시점부터 SAVEPOINT까지만 일부 롤백 가능
- SETTRANSACTION
    - 트랜잭션 지정

## Reference

[https://iamfreeman.tistory.com/entry/DBMS-데이터-언어-DDL-DML-DCL-TCL-의-정의](https://iamfreeman.tistory.com/entry/DBMS-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%96%B8%EC%96%B4-DDL-DML-DCL-TCL-%EC%9D%98-%EC%A0%95%EC%9D%98)