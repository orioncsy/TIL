# Semaphore & Mutex

## Critical section

### 개념

- 여러 프로세스나 스레드가 공유된 자원을 접근하는 코드 블록
- 공유된 자원을 동시에 접근하면 문제가 발생할 수 있다.

## Semaphore

### 개념

- critical section에서 발생하는 문제를 해결하기 위한 개념
- 공유 자원에 대한 접근이 가능한 프로세스나 스레드의 수를 변수로 제한
- 운영체제나 커널에 변수를 저장하고 프로세스가 이 값을 확인 및 변경 가능
- 세마포어가 5라면 접근할 수 있는 프로세스는 5개이다.

## Mutex

### 개념

- MUTual EXclusion의 약자로 binary semaphore로 불린다.
- 단 하나의 프로세스나 스레드가 접근 가능하다.
- 사용 중인 프로세스나 스레드가 lock을 걸고 unlock도 해당 프로세스만 가능하다.
- 뮤텍스는 운영체제나 커널에 저장되고 변경되는 세마포어와 다르게 프로세스에서 관리

### 알고리즘

- 데커 알고리즘
    - flag와 turn 변수를 사용하여 임계구역에 들어갈 프로세스나 스레드 결정
    - flag에는 누가 진입할지를 bool 배열 형태로 정하고, turn에는 차례를 저장
    - turn이 자기 차례가 아니면 반복문으로 대기하고 자기 차례면 임계 구역 실행
- 피터슨 알고리즘
    - 데커와 비슷하나 다른 프로세스에게 진입 기회를 양보하는 방식
- 제과점 알고리즘
    - 번호표를 받는 방식
    - 더 작은 수의 번호표를 가지고 있다면 임계 구역 실행

## 차이점

- 뮤텍스는 동기화 대상이 1개일 때, 세마포어는 1개 이상일 때 사용
- 뮤텍스는 자원의 소유 및 책임을 지는데 세마포어는 자원 소유 불가
- 뮤텍스는 소유하고 있는 프로세스나 스레드만 unlock할 수 있으나 세마포어는 다른 프로세스나 스레드가 가능
- 뮤텍스는 운영체제나 커널에 저장되어 시스템 전반에 걸쳐 적용되고 파일 시스템 상 파일로 존재한다.
- 세마포어는 프로세스 범위로 적용되어 프로세스가 끝나면 자동으로 clean up

## Reference

[세마포어(Semaphore)와 뮤텍스(Mutex)](https://tibetsandfox.tistory.com/45)

[https://gyoogle.dev/blog/computer-science/operating-system/Semaphore & Mutex.html](https://gyoogle.dev/blog/computer-science/operating-system/Semaphore%20&%20Mutex.html)