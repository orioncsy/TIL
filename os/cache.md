# Cache

## 개념

### Principle of Locality

- 자주 사용하는 데이터에 대한 지역성
    - 시간 지역성 - 최근 접근한 데이터를 다시 접근
    - 공간 지역성 - 최근 접근한 데이터의 주변 공간에 접근

### Cache

- L1 cache
    - 프로세서와 가장 가깝고 빠른 속도이며 용량이 제일 적다
    - instruction cache(text 영역), data cache(text 외 영역)로 구분
- L2 cache
    - L1 캐시처럼 나뉘지 않는 보다 큰 용량
- L3 cache
    - 멀티코어에서 여러 코어가 공유하는 캐시

### Cache matrix

- 캐시 성능 측정
- hit latency - 캐시에서 찾고자 하는 데이터를 찾을 때 걸리는 시간
- miss latency - cache miss가 발생해 상위 캐시에서 데이터를 찾아오는 데 걸리는 시간
- average access time = hit latency + miss rate * miss latency
- miss rate=cache miss / cache access

## 구성

### 종류

- 캐시는 SRAM(static random access memory)로 주소가 key로 주어지면 해당 공간에 바로 접근 가능
- 메인 메모리는 DRAM(dynamic random access memory)로 동일하지만 속도가 더 느리다.
- 캐시는 해시 테이블을 사용하여 시간 복잡도가 O(1) 수준이다.
- 캐시는 캐시 블록으로 구성되어 key로 접근 가능하고, 블록의 개수와 크기가 캐시 크기를 결정

### indexing

- 1024개의 캐시 블록의 크기가 각 32B일 때, 주소 값은 하위 5비트를 offset으로 두고 10비트를 캐시 블록을 구분하기 위해 사용

### Tag

- 인덱스 중복을 피하기 위해 남은 비트를 사용한다.
- valid bit를 확인하여 1일 경우 태그 필드와 주소의 필드가 같은 지 확인하고 같으면 히트
- 만약 유효 비트가 0이면 미스가 발생할 경우 주소를 태그 필드를 작성하고 데이터 필드도 작성해서 유효 비트를 1로 설정
- 태그가 일치하지 않는 경우 교체 정책을 사용
- 태그는 저장공간으로 인식되지 않고 오버헤드로 본다.

## Associate Cache

### cache 종류

- 서로 다른 주소가 같은 인덱스를 가져 계속 교체를 하면 계속 데이터를 바꾸는 핑퐁 문제 발생 가능
- 인덱스가 가리키는 블록의 형태에 따라 분류
    - direct mapped - 인덱스가 가리키는 공간이 하나인 경우 빠르지만 충돌 잦다.
    - fully associated - 인덱스가 모든 곳을 가리킬 경우 속도가 느리다.
    - set associated - 인덱스가 가리키는 공간이 두 개 이상일 경우

### Set associate cache

- two way set associative
    - 인덱스를 통해 블록에 접근하는 것은 동일하지만 2개의 블록을 모두 확인해야 한다.

### Cache Write

- 캐시에서 저장된 데이터 값을 변경할 때 메모리에 반영되는 시기에 따라 두 가지 정책 존재
- write through
    - 캐시에 데이터가 업데이트될 때마다 메모리에 반영
    - 주로 write no allocate와 함께 사용
        - write no allocate는 캐시 미스(캐시에 값을 적으려고 하는데 존재하지 않을 경우)가 발생 시 메인 메모리에 바로 write 하는 방식
    - 캐시가 항상 업데이트된 상태이기 때문에 메인 메모리에 바로 값을 작성하여도 괜찮기 때문에 사용
- write back
    - 캐시가 교체되어 나갈 때 메모리에 반영되는 방식
    - 주로 write allocate와 동시에 사용
        - write allocate는 캐시 미스 발생 시 메인 메모리의 값을 캐시와 가져와 write 하는 방식
    - 캐시 값이 항상 갱신되어 있는 상태가 아니기 때문에 메인 메모리에 바로 사용할 수 없어서 두 정책을 사용

### 코드 작성 측면

- 코드 작성하는 측면에 있어서도 캐시를 적용할 수 있다.
- 이중 루프를 돌 때 데이터의 공간 지역성을 따질 때 바깥 루프문을 row로 설정하는 것이 효율적이다.
- 시간 지역성을 따질 때 cache 사이즈보다 커지면 캐시미스가 계속 발생하기 때문에 반복문을 사용할 때 cache 사이즈 단위로 반복하는 코드를 구현하는 것이 효율적이다.

## Reference

[💵 캐시가 동작하는 아주 구체적인 원리: 하드웨어로 구현한 해시 테이블](https://parksb.github.io/article/29.html)