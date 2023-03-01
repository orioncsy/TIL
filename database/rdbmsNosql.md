# RDBMS & NoSQL

## 개념

### RDBMS

- 관계형 데이터베이스 관리 시스템
- 모든 데이터를 2차원 테이블 형태로 표현하는 데이터베이스
- 다른 테이블들간의 관계를 맺고 모여 있는 집합체

### NoSQL

- Not only SQL
- RDBMS와 달리 테이블들 간의 관계를 정의하지 않고 구조화되지 않아 자유롭게 데이터 처리
- 분산형 데이터 베이스를 지원
- 종류
    - key-value model
        - 키- 값의 형태로 데이터를 저장
        - 고속으로 읽고 쓰기가 가능
        - redis가 대표적
    - document model
        - 하나의 키에 구조화된 문서를 저장하고 조회
        - 문서 id에 대한 인덱스를 형성하여 O(1)시간으로 조회 가능
        - B tree 인덱스를 사용하기 때문에 데이터를 입력, 삭제할 때 성능이 떨어진다.
        - 중앙 집중식 로그 저장, 타임라인 저장, 통계 정보 저장에 사용
        - mongoDB
    - column model
        - 하나의 키에 여러 개의 컬럼 이름과 컬럼 쌍으로 이루어진 데이터를 저장 및 조회
        - key는 키 값과 column-family, column-name을 가지고 속성이 계층적인 구조를 가진다.
        - 쓰기에 더 특화되어 있어 쓰기가 많은 서비스 및 대량 데이터 입력 및 조회하는 서비스에 사용
        - 채팅 내용, 실시간 분석을 위한 저장에 사용
        - Hbase
    - graph model
        - 데이터를 그래프 형태로 저장
        - Neo4J

## CAP

### 개념

- noSQL 같은 분산형 데이터베이스에서 consistency, availabilty, partition tolerance를 모두 성립할 수 없다는 이론

### Consistency - 일관성

- 여러 데이터베이스에게 요청을 해도 같은 데이터를 받을 수 있는 상태

### Availability - 가용성

- 언제 어느 순간에도 요청에 대한 응답을 받을 수 있는 상태

### Partition tolerance - 분할 허용성

- 데이터베이스간 통신이 끊긴 상태에서 시스템이 동작하는 상태

### 특징

- 분할이 이루어졌을 때 일관성을 가지면 가용성을 희생하고, 가용성을 가지면 일관성을 희생해야 한다.
- 데이터베이스간 통신이 끊기면, 같은 데이터를 제공하기 위해 통신이 재연결될 때까지 기다려 가용성 희생
- 데이터베이스간 통신이 끊기면, 즉시 대응하기 위해 일관성을 희생하고 가지고 있는 데이터를 제공

## Reference

[https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/Database](https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/Database)