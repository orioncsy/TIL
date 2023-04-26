# PCB

## 개념

### Process Management

- CPU가 여러 프로세스를 스케줄링을 통해 관리하는 것

### Process Metadata

- 프로세스가 생성되면 관련 정보들을 PCB에 저장
- process ID, process state, process priority, CPU registers, owner, CPU usage, memory usage

### PCB(Process Control Block)

- process metadata를 저장하는 공간
- 하나의 프로세스 정보를 저장

### 프로그램 실행 과정

- 프로그램 실행
- 프로세스 생성
- 각 프로세스 주소 공간에 코드 부분, 데이터 부분, 스택 부분 생성
- 프로세스의 메타데이터를 pcb에 저장

### 사용 목적

- CPU가 프로세스 교체 작업을 진행
- 인터럽트가 발생하면 기존에 실행되던 프로세스 정보를 PCB에 저장하고 다른 프로세스 실행

### 관리 방식

- Linked List 방식
- PCB list head에 PCB들이 연결
- 주소값을 연결하기 때문에 삽입, 삭제 용이

## Context Switching

### 개념

- CPU가 이전의 프로세스 정보를 PCB에 저장하고 다른 프로세스의 정보를 PCB로부터 읽어 레지스터에 적재하는 과정
- 입출력 등의 이벤트로 인해 cpu가 대기 상태인 시간을 효율적으로 사용하기 위해 다른 프로세스를 가져와 작업을 처리하는 목적

### 발생 상황

- 인터럽트 발생
- 실행 중인 프로세스의 CPU 할당 시간 초과
- 입출력을 위한 대기

### Overhead

- context switching을 하게 되면 프로세스 정보를 저장하고 다른 프로세스 정보를 가져오는 과정에서 overhaed 발생
- 대기 시간 동안 다른 프로세스를 처리하기 위해 context switching을 하게 되고 그 과정에서 발생하는 overhead 감수

## Reference

[https://gyoogle.dev/blog/computer-science/operating-system/PCB%20&%20Context%20Switching.html](https://gyoogle.dev/blog/computer-science/operating-system/PCB%20&%20Context%20Switching.html)