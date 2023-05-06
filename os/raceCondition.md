# Race Condition

## 개념

### 경쟁 상태

- 공유 자원에 대하여 여러 프로세스가 접근하려고 하여 결괏값에 영향을 줄 수 있는 상황

## Race Condition 사례

### 커널 작업 도중 인터럽트 발생

- 발생 상황
    - 커널 모드에서 데이터를 로드하여 작업하다 인터럽트가 발생하여 해당 데이터를 조작하는 경우
- 해결 방법
    - 커널 모드에서 작업하는 상태에서는 인터럽트를 disabled시켜서 CPU 제어권을 막는다.

### System call을 통하여 커널 모드에서 context switching 발생

- 발생 상황
    - 프로세스가 system call을 통해 커널 모드에서 작업하다가 context switching이 발생하여 다른 프로세스가 CPU 제어권을 가져가서 공유 자원에 접근하는 경우
- 해결 방법
    - 프로세스가 커널모드에서 작업하는 경우 시간 초과가 일어나도 다른 프로세스가 CPU 제어권을 획득하지 못하도록 한다.

### 멀티 프로세서 환경에서 공유 메모리 내 커널 데이터 접근

- 발생 상황
    - 멀티 프로세서 환경에서 2개의 CPU가 동시에 커널 내 공유 데이터에 접근하는 경우
- 해결 방법
    - 커널 내부에 있는 공유 데이터를 접근할 때 해당 데이터에 대하여 lock, unlock을 걸어 다른 프로세서의 접근을 제한

## Reference

[https://gyoogle.dev/blog/computer-science/operating-system/Race%20Condition.html](https://gyoogle.dev/blog/computer-science/operating-system/Race%20Condition.html)