# Process

## 개념

### process

- 운영체제에서 일련의 작업 단위
- 프로그램은 파일이 저장 장치에 저장되어 있고 메모리에 올라와 있지 않은 정적인 상태
- 프로그램을 실행시켜 OS로부터 자원을 할당받아 실행되는 상태를 프로세스
- 메모리에 올라와 있고 실행 중이며 OS로 부터 자원을 할당받고 PCB에 정보가 담기고 CPU 제어권을 받은 상태

### 프로세스 메모리 구조

- OS kernel space - 드라이버
- stack - 지역 변수, 매개변수, LIFO 방식, 높은 주소에서 낮은 주소로 할당
- heap - 동적 메모리, FIFO 방식, 낮은 주소에서 높은 주소로 할당
- BSS(Block Started by Symbol) - 초기화 되지 않은 변수를 저장
- Data - 전역 변수를 저장
- text - 상수, 실행할 코드 저장

### 오버 플로우

- 한정된 메모리 공간이 부족한 상태
- 스택과 힙이 영역을 침번할 경우 발생
- 힙 오버플로우 - 힙이 스택 영역을 침범하는 경우
- 스택 오버플로우 - 스택이 힙 영역을 침범하는 경우

### 프로세스 상태

- new - 프로세스 생성
- ready - 프로세스 할당 대기
- running - 프로세스 실행 상태
- waiting - 프로세스가 이벤트를 기다리는 상태
- terminated - 프로세스 종료 상태
- admiited - 생성에서 준비. 준비 큐가 비어있을 때 작업 스케줄러에 의해 실행
- dispatch - 준비에서 실행, 준비 큐 맨 앞에 있는 작업에게 cpu 할당
- blocked - 실행에서 대기, 프로세스가 작업 등으로 인해 명령을 실행을 멈춘 상태
- wake up - 대기에서 준비, block 상태에서 작업이 끝나면 대기에서 준비로 바뀐 상태
- interrupt - 실행에서 준비, timer run out으로 할당받은 시간이 끝나거나 스케줄러에 의해 다른 우선순위가 높은 작업이 dispatch 된 상태
- exit - 실행에서 종료, 프로세스가 cpu를 할당받아서 작업을 마친 상태

### Context Switching

- 하나의 프로세스에서 다른 프로세스로 cpu 제어권이 넘어가는 경우
- 프로세스가 cpu를 할당 받고 작업하다 interrupt가 발생하면 cpu 제어권이 운영체제로 넘어가고 context를 저장하고 다른 프로세스에게 cpu 이양
- 빈번한 context switching은 오버헤드 발생

### 프로세스 제어 블록(PCB)

- os가 프로세스를 관리하기 위해 프로세스마다 관련 정보를 담는 커널 내의 자료구조
- 프로세스 식별자(process id) - PID
- 프로세스 상태 - cpu 할당 가능 여부
- PC(program counter) - 다음 명령어 수행할 위치
- 레지스터 - 레지스터 관련 정보
- 프로세서 스케줄링 정보 - 우선순위, 스케줄 큐에 대한 포인터, 다른 스케줄 매개변수
- 계정 정보 - cpu 사용 시간, 계정 번호
- 입출력 상태 관련 정보 - 프로세스에 할당된 입출력 장치들과 열린 파일 목록

## Reference

[[ OS] 프로세스의 개념, 상태, 제어](https://cocoon1787.tistory.com/848)