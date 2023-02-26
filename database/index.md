# Index

## 개념

### DB index

- 일종의 색인 개념으로 데이터베이스에서 검색 속도를 향상하기 위해 사용
- 칼럼 값과 레코드 저장 주소를 한 쌍으로 인덱스를 만들어 파일로 저장하는 방식
- 인덱스는 항상 정렬 상태를 유지
  - 이 때문에 삽입, 수정, 삭제는 조회보다 시간 복잡도에 손해가 있다.
  - 저장 성능을 손해 보고 검색 속도를 향상

## 종류

### Sparse vs dense

- sparse index
  - 모든 레코드에 대한 주소가 없는 경우
- dense
  - 모든 레코드에 대한 주소가 있는 경우

### Primary index

- Primary key와 물리적 레코드 block의 주소를 포인터 형식으로 가지고 있다.
- 정렬 상태를 유지하고 있다.
- sparse index로 모든 레코드에 대해 주소를 가지지 않고 block의 주소값을 가지고 있다.
- pk 값에 따라서 레코드 저장 위치가 결정되어 pk 값이 변경되면 위치도 바뀐다.
- pk에 하나만 적용되기 때문에 테이블 당 하나만 설정 가능하다.

### Clustering Index

- Clustered
  - index에서 clustered는 비슷한 데이터(물리적으로 인접한 데이터)를 묶어서 저장하는 형태이다.
  - 비슷한 값을 동시에 조회하는 경우가 많아서 사용한다.
- Clustered index
  - 테이블의 primary key에 대해서만 적용하여 pk 값이 비슷한 레코드들끼리 묶는 저장하는 것이다.
  - pk 값에 따라서 레코드 저장 위치가 결정되어 pk 값이 변경되면 위치도 바뀐다.
  - pk에 하나만 적용되기 때문에 테이블 당 하나만 설정 가능하다.
  - sparse index에 해당한다.
  - 정렬 상태 유지

### Secondary index

- 인덱스를 보조하는 인덱스
  - 검색을 빠르게 하기 위해 pk로 검색하지 않고 다른 필드에 인덱스를 걸 수 있다.
- 테이블 당 여러 인덱스를 가질 수 있고 정렬되지 않은 상태이다.
- record 당 하나의 주소값을 가져 desnse index에 해당

## 알고리즘 및 과정

### 사용되는 알고리즘

- B+ - tree index algorithm
  - 일반적으로 사용되는 알고리즘으로 칼럼의 값을 변경하지 않고 원래 값으로 인덱싱하는 방식
  - B+ 트리는 균형 트리로 리프 노드에 데이터의 값을 넣고 노드를 색인으로 두고 값을 찾으며 리프 노드는 linkedList로 연결되어 순차 접근, 임의 접근의 성능 모두 뛰어난 자료구조이다.
- Hash index algorithm
  - 해싱 기법을 사용하여 칼럼을 해시 함수를 통해 해시 값으로 변형하여 테이블에 저장하는 방식
  - 빠른 알고리즘으로 평균 O(1)의 시간 복잡도를 가질 수 있다.
  - 값을 변형해서 사용하기 때문에 일부 값을 통한 검색이 불가능하다.
  - 주로 memory DB에서 사용
- B+ 트리를 사용하는 이유
  - 해시를 사용하면 O(1)로 빠른 속도로 접근할 수 있지만 select 조건에 부등호가 사용될 경우 해시는 문제가 발생할 수 있다.

### 과정

- table을 생성하면 MYD, MYI, FRM 파일 생성
  - FRM - 테이블 구조가 저장
  - MYD - 실제 데이터 저장
  - MYI - 인덱스 정보 저장
- INDEX를 사용하지 않으면 MYI 파일은 비워져 있다.
- 사용자가 SELECT 쿼리로 INDEX를 사용하는 COLUMN을 탐색할 때 MYI 파일을 탐색

## DML 발생 상황

### INSERT

- Index에 대한 데이터를 추가해야 하는 오버헤드 발생

### DELETE

- 테이블에서 데이터가 지워지만 빈 공간에 다른 데이터 추가 가능
- 그러나 INDEX 에서는 사용 안 함으로 처리되어 공간을 차지하는 문제 발생

### UPDATE

- 테이블에서 UPDATE가 발생하면 INDEX에서는 UPDATE 불가
- 인덱스에서는 DELETE하고 INSERT 하는 방식으로 기존 공간을 사용 안 함으로 처리하는 문제 발생

## 장단점 및 최적 사용

### 장단점

- 검색 속도 향상에 좋지만 .mdb 파일 용량이 커진다.
- 인덱스된 필드에서 추가, 삭제 작업을 하면 성능이 떨어진다.
- 데이터 변경을 자주 하면 index를 재작업해야 해서 성능이 떨어진다.

### 최적 사용

- 사용하기 좋은 경우
  - where 절에서 자주 사용하는 column
  - 외래키가 사용되는 column
  - join이 자주 사용되는 column
- index를 사용하지 않으면 좋은 경우
  - data 중복도가 높은 column
  - DML이 자주 일어나는 column

## Reference

[Index | 👨🏻‍💻 Tech Interview](https://gyoogle.dev/blog/computer-science/data-base/Index-.html)

[Interview_Question_for_Beginner/Database at master · JaeYeopHan/Interview_Question_for_Beginner](https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/Database)

[https://tcachu.tistory.com/12](https://tcachu.tistory.com/12)