# Collection

## 개념

### Collection

- 자바에서 자료구조를 기반으로 한 데이터의 모음 또는 집합

### JCF(Java Collection Framework)

- 자바의 컬렉션을 정의하고 이를 구현하는 인터페이스 제공

## 종류

### Collection

- List와 Set으로 구성

### List

- ArrayList
    - 단방향 포인터 구조로 데이터에 대한 인덱스를 가지고 있어 조회 성능이 뛰어남
    - 동적 배열 제공
- Vector
    - ArrayList에서 동기화 처리가 발생하여 속도가 ArrayList에 비해 느리다.
    - 멀티 스레드 환경에서 사용
- LinkedList
    - 양방향 포인터 구조로 데이터의 삽입, 삭제가 빈번할 경우 효율적
    - queue를 구현할 때 사용
- Stack
    - 스택 자료구조를 구현
    - 후입선출을 기본으로 한다.

### Set

- HashSet
    - 순서가 보장되지 않고 중복을 허용하지 않는다.
    - 임의 접근 속도가 빠르다.
- TreeSet
    - 정렬 방법 지정 가능

### Map

- key-value 형태로 데이터를 저장하고 순서가 보장되지 않으며 key는 중복 불가이지만 value는 중복 허용
- HashTable
    - 동기화를 지원하고 null 값 불가
- HashSet
    - 동기화를 지원하지 않고 null 값 허용
- TreeMap
    - 정렬 방법 지정 가능

## Reference

[https://gangnam-americano.tistory.com/41](https://gangnam-americano.tistory.com/41)