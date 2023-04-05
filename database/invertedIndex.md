# Inverted Index

## 개념

### Inverted Index(역인덱스)

- 내용과 그것이 위치한 위치를 자료구조로 표현한 것

### 인덱스와의 차이

- 방향성에 차이가 존재
- 인덱스는 doc Id와 내용을 매핑하지만 역 인덱스는 내용과 그 내용이 위치한 doc Id를 매핑한다.

## 검색 방식

### 인덱스

- 전통적인 RDBMS에서는 like 검색을 사용
- 매핑되는 내용 중에 찾으려는 내용을 row마다 탐색한다.
- 데이터가 많으면 검색 대상이 증가하여 검색 시간이 증가한다.

### 역인덱스

- elastic search에서 사용
- 데이터를 저장할 때 내용을 파싱 하여 추출된 키워드를 텀(term)이라고 하고 이 키워드를 통해 검색
- 데이터가 늘어나도 역인덱스가 가리키는 id가 증가하기 때문에 탐색 속도가 상대적으로 빠르다.

## Reference

[https://esbook.kimjmin.net/06-text-analysis/6.1-indexing-data](https://esbook.kimjmin.net/06-text-analysis/6.1-indexing-data)

[https://medium.com/@lunay0ung/basics-인덱스와-역인덱스-inverted-index-a95573836189](https://medium.com/@lunay0ung/basics-%EC%9D%B8%EB%8D%B1%EC%8A%A4%EC%99%80-%EC%97%AD%EC%9D%B8%EB%8D%B1%EC%8A%A4-inverted-index-a95573836189)