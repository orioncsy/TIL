# Load Balancing

## 개념

### Scale out & Scale up

- 웹 사이트 접근 인원이 증가하면서 모든 트래픽을 1대의 서버로 감당하기가 어려워짐
- Scale up을 통해 서버의 성능을 향상하거나 Scale out을 통해 여러 대의 서버로 분산시켜 작업하는 방법으로 대용량 트래픽 해소
- scale up을 통한 하드웨어 향상 비용이 크고 한계가 있으며 서버에 문제가 생기면 서비스가 중단될 수 있다.
- scale out을 통한 여러 대의 서버로 트래픽을 분산시키면 무중단 서비스를 제공 가능

### Load Balancing

- 일종의 scale out으로 여러 대의 서버에 트래픽을 분산시켜 주는 기술
- load balancer를 서버와 클라이언트 사이에 두고 부하를 분산시켜준다.
- 서버를 추가로 증설하면서 load balancer로 관리하여 서버 부하 해결

## 작동 방식

### Round Robin

- CPU 스케줄링 중 round robin과 유사
    - 시분할 시스템을 위해 설계된 선점형 스케줄링
    - 프로세스들 사이에 우선순위를 두지 않고 순서대로 시간단위로 CPU를 할당하는 방식

### Least Connections

- 연결 개수가 적은 서버를 선택하는 방식
- 트래픽으로 세션이 길어지는 경우 권장되는 방식

### Source

- 사용자 IP를 해싱하여 분배하는 방식
- 특정 사용자가 항상 같은 서버로 연결되는 것을 보장

## Reference

[https://gyoogle.dev/blog/computer-science/network/Load%20Balancing.html](https://gyoogle.dev/blog/computer-science/network/Load%20Balancing.html)