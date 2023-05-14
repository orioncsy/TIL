# Von Neumann Architecture

## 개념

### 폰 노이만 구조

- 존 폰 노이만이 개발한 내장 메모리 순차 처리 방식
- 프로그램과 데이터를 하나의 메모리에 저장하여 사용하는 방식
- 데이터는 읽고 쓰기가 가능하나, 명령어는 읽기만 가능
- CPU와 하나의 메모리를 사용하는 현대 컴퓨터 구조에서 사용하는 모델

## 장단점

### 장점

- 하드웨어의 재배치가 필요 없어 소프트웨어 교체만 하면 된다.
- 범용성이 뛰어나 현대 컴퓨터 모델로 많이 사용한다.

### 단점

- 메모리와 CPU를 연결하는 버스가 하나이기 때문에 여러 작업을 동시에 처리하지 못한다.
- 이 때문에 순차적 처리를 하는 방식을 사용하여 고속 병렬처리가 불가능하다.
- CPU가 명령어를 읽는 동시에 메모리에 있는 데이터에 접근이 불가능

### 해결법

- Harvard architecture(하버드 구조)
    - 명령용 버스와 데이터용 버스를 물리적으로 분할한 컴퓨터 아키텍처

## Reference

[https://gyoogle.dev/blog/linux/Von%20Neumann%20Architecture.html](https://gyoogle.dev/blog/linux/Von%20Neumann%20Architecture.html)