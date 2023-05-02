# CPU Scheduling

## 개념

### Scheduling

- CPU를 효율적으로 사용하기 위하여 프로세스를 적절히 할당하는 방식
- Batch time
    - 최대한 많은 일을 하는 것이 목표
- Interactive system
    - 빠른 시간 안에 응답하고 적은 대기 시간을 가지는 것을 목표
- Real time system
    - 기한을 맞추는 것을 목표

### 선점형 스케줄링

- OS가 프로세스 작업을 강제 회수할 수 있는 권한을 가지는 경우

### 비선점형 스케줄링

- 프로세스 종료나 이벤트가 발생할 때까지 보장

## 프로세스 상태 전이

### 승인(Admitted)

- 프로세스 생성이 가능하여 승인

### 스케줄러 디스패치(Scheduler Dispatch)

- 준비 상태의 프로세스를 선택하여 실행

### 인터럽트(Interrupt)

- 이벤트가 발생하여 프로세스 상태를 실행에서 준비 상태로 바꾸고 해당 작업을 먼저 처리

### 입출력 또는 이벤트 대기

- 실행 중인 프로세스가 입출력 또는 이벤트로 인하여 대기 상태로 바뀌는 상태

### 입출력 또는 이벤트 종료

- 입출력이나 이벤트로 대기 상태였던 프로세스가 종료되는 경우 대기 중이었던 프로세스를 준비 상태로 변경

## 종류

### 비선점형

- FCFS(First Come First Served)
    - 큐에 도착한 순서대로 할당
    - 실행 시간이 긴 작업이 초반에 들어오면 대기 시간이 길어진다.
- SJF(Shortest Job First)
    - 수행 시간이 짧은 작업을 먼저 수행
    - FCFS보다 평균 대기 시간이 짧다.
- HRN(Highest Response-ratio Next)
    - SJF를 보완하여 우선순위를 계산하여 점유 불평등 해소
    - 우선순위는 대기시간+실행시간을 실행시간으로 나눈 값이다.

### 선점형

- Priority Scheduling
    - 우선순위를 부여하여 그 순서대로 처리
    - 우선순위가 낮은 프로세스는 기아현상이 발생 가능
    - 일정 시간을 기다리면 우선순위를 한 단계 높여주는 aging 기법을 사용하여 단점 해소
- Round Robin
    - FCFS 방식으로 프로세스를 처리하고 Time Quantum 만큼 CPU를 할당받는다.
    - 할당받은 시간이 커지면 FCFS와 유사해지고, 짧아지면 잦은 context switching으로 오버헤드가 크게 발생
- Multilevel-queue
    - 작업을 여러 종류로 나누고 여러 개의 큐를 사용하는 방식
    - 우선순위가 높은 쪽에는 작은 time quantum을 주고 낮은 곳은 높은 time quantum을 준다.
- Multilevel FeedBack Queue
    - time quantum을 다 채운 프로세스는 한 단계 아래에 있는 큐에 넘겨주고 마지막은 FCFS 방식으로 처리
    - 마지막으로 간 프로세스는 CPU burst일 가능성이 높다.
    - 우선순위가 낮은 프로세스가 할당을 받지 못하는 기아 상태가 발생 가능
        - aging 기법으로 해결 가능
    - turnaround 평균 시간을 줄일 수 있고, response time도 짧아진다.

## 성능 지표

### Response time

- 작업이 처음 시작되기까지 시간

### Turnaround time

- 실행 시간과 대기 시간을 모두 합한 시

## Reference

[https://gyoogle.dev/blog/computer-science/operating-system/CPU%20Scheduling.html](https://gyoogle.dev/blog/computer-science/operating-system/CPU%20Scheduling.html)