# Virtual memory

## Memory

### 개념

- 프로그램을 실행할 때 데이터나 코드를 저장하는 공간
- 주기억 장치 - dram, cache, register
- 보조기억 장치 - ssd, hdd

### 가상 메모리

### 개념

- 실제 메모리보다 많아 보이게 하는 기술로 어떤 프로세스가 실행될 때 프로세스 전체가 메모리에 올라가지 않는다.
- 일부분만 메모리에 올려놓고 나머지는 보조 기억 장치에 저장

### MMU

- Memory Management Unit
- 가상 주소를 물리적 주소로 변환
- 모든 가상 주소를 변환하면 부하가 크기 때문에 ram을 page로 나누어서 처리

### 요구 페이징

- CPU가 요구할 때 데이터를 메모리에 올리는 것

### Page fault

- 어떤 프로그램이 가상 메모리상의 데이터에 접근하려고 하지만 실제 메모리에는 부재할 경우 발생
- 운영체제에서 데이터를 메모리에 가져와서 다시 명령 실행
- 페이지 폴트가 잦으면 성능이 떨어지기 때문에 페이지 교체 정책이 존재
    - 메모리가 다 차있을 때 기존 페이지 중 하나를 보조 기억 장치로 내리고 새로운 페이지를 메모리에 올리는 알고리즘

### ****page replacement algorithm****

- FIFO(firt in firt out)
    - 처음 메모리에 올라온 페이지를 제거.
- OPT(optiomal replacement)
    - 미래에 가장 사용 안될 페이지를 제거.
- LRU(least recently used)
    - 최근에 가장 오랫동안 사용하지 않은 페이지 제거
- LFU(least frequently used)
    - 자주 사용하지 않은 페이지 제거

### TLB

- Translation Lookaside Buffer
- 가상 메모리 주소를 물리 주소로 변환하는 속도를 높이기 위한 캐시
- 가상 메모리와 물리 주소를 변환 테이블에 저장하고 CPU가 가상 주소로 접근할 때 TLB를 먼저 살피고 없으면 MMU가 페이지 테이블에 해당하는 물리 주소로 변환 후 접근
- MMU에 포함된 작은 캐시 메모리

## Reference

[[운영체제] 가상 메모리(Virtual Memory System)](https://ahnanne.tistory.com/15)