# MongoDB

## 개념

### MongoDB

- 오픈소스 비관계형 데이터베이스
- NoSQL 중 document 형태의 DB

### 특징

- Document oriented storage
    - 모든 데이터가 json으로 저장되며 스키마가 없다.
- 스키마가 없어 다양한 타입의 데이터를 저장 가능
- 복잡한 구조를 쉽게 저장하고 join을 사용하지 않는다.
- full index support
    - 인덱싱 기능으로 빠르게 조회
- replication & high availability
    - 데이터 복제를 통한 가용성 향상
- auto sharing
    - 기본키를 기반으로 여러 서버에 데이터를 나누는 scale out
- querying
    - key 기반의 다양한 종류의 쿼리 제공
- fast in-place update
    - 고성능 atomic operation 지원
- map reduce
    - map이라는 방식으로 데이터의 key value 추출
    - reduce로 추출한 데이터 정제
- GridFS
    - 별도의 스토리지 엔진으로 파일 저장
    - 기본 스토리지 엔진인 wired tiger는 높은 쓰기 성능 및 압축을 제공
    - 별개의 인메모리와 암호화 데이터스토어 기능
    - 스파크 커넥터를 제공하여 대용량 인메모리 분석 지원

## MongoDB 구조

### 전체적인 구조

- 데이터베이스
    - 몽고db 안에 여러 데이터베이스 존재
- 컬렉션
    - 하나의 데이터베이스에 여러 컬렉션 존재
    - 하나의 컬렉션에 여러 document를 포함
        - 동적인 스키마를 가지고 있어 다양한 형태의 document 존재
- document
    - 하나의 컬렉션 안에 여러 개의 document 존재
    - 데이터 구조는 1개 이상의 key-value 쌍으로 구성
    - 컬렉션 안에 다양한 스키마의 document 존재
    - id 값은 document의 유일한 값을 정한다.

## MongoDB 장단점

### 장점

- flexiblity
    - 스키마가 없기 때문에 어떤 형태의 데이터도 저장이 가능하다.
- performance
    - 읽고 쓰기 성능이 뛰어나 캐싱이나 많은 트래픽에서 사용 가능
- scalability
    - 초기 스케일 아웃 구조(auto sharing)를 통해 쉽게 운용

### 단점

- join이 없어 join 없이 데이터 구조화 필요
- memory mapped file로 파일 엔진 db이다. 메모리를 os에게 위임하는 형태
    - 메모리에 의존적이여서 메모리에 따라 성능 좌우
- SQL을 완전히 이전하기 어렵다.
- B트리 인덱스를 사용하고 있기 때문에 크기가 커질수록 새로운 데이터 삽입, 삭제 시 성능 저하
    - 데이터를 저장하고 조회할 때 적합

## Reference

[https://hwanine.github.io/database/MongoDB/](https://hwanine.github.io/database/MongoDB/)