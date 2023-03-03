# Elastic Search

## 개념

### Elastic Search

- Apache Lucene 기반 java 오픈소스 분산 검색 엔진
- 많은 데이터를 신속하고 실시간으로 저장, 검색, 분석 가능

## ELK

### Logstash

- CS 파일이나 DB 같은 다양한 소스의 로그 또는 트랜잭션 데이터를 수집, 집계, 파싱 하여 Elastic search로 전달

### Elastic search

- Logstash로부터 받은 데이터를 검색 및 집계하여 필요한 정보 획득

### Kibana

- Elastic Search로부터 찾은 데이터를 시각화 및 모니터링

## 용어

### RDB와 비교한 용어

- database - index
- table - type
- column - field
- row - document

### 아키텍쳐 용어

- 클러스터
    - Elastic search에서 가장 큰 시스템 단위
    - 하나 이상의 노드로 구성되고 서로 다른 클러스터는 독립적
    - 여러 서버가 하나의 클러스터를 구성할 수 있고, 하나의 서버가 여러 클러스터 구성 가능
- 노드
    - 하나의 프로세스 단위
    - master eligible
        - 클러스터를 제어하는 마스터로 선택할 수 있는 노드
        - 인덱스 생성, 삭제
        - 클러스터 노드 추적, 관리
        - 데이터 입력 시 샤드 할당 설정
    - data node
        - CRUD와 관련이 있는 노드
    - ingest node
        - 사전 처리 파이프라인 실행
    - coordination only node
        - data node, master eligible node를 대신하는 역할
        - 로드밸런서와 유사한 기능
- 인덱스
    - RDBMS에서 database와 유사한 개념
- sharding(샤딩)
    - 스케일 아웃을 위해 인덱스를 여러 조각으로 나눈 것
- replica
    - 노드의 손실을 대비해 샤드를 복제하는 곳

### 특징

- scale out
    - 샤드를 통해 수평적으로 확장
- 고가용성
    - replica를 통한 데이터 안정성
- schema free
    - json 문서를 통해 데이터 검색을 하기 때문에 스키마 개념이 없다.
- restful
    - 데이터 CRUD 작업은 http restful API를 통해 수행
    - select - get
    - insert - put
    - update - post
    - delete - delete

### 역색인(inverted index)

- 텍스트를 파싱 해서 검색어 사전을 만들고 inverted index 방식으로 텍스트 저장
- RDBMS의 like는 데이터가 많을수록 검색 시간이 오래 걸리지만 역 인덱스를 사용하면 전문 탐색이 더 빠르다.

## Reference

[https://victorydntmd.tistory.com/308](https://victorydntmd.tistory.com/308)