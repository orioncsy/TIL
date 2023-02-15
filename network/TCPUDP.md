# TCP와 UDP의 차이

## 개요

- TCP와 UDP는 OSI 7계층 중에 Transport layer에 해당하는 프로토콜이다.
- 데이터를 전달하는 역할을 담당하고 패킷 오류 검출, 재전송을 처리한다.

## TCP(Transmission Control Protocol)

### 개념

- 연결 지향 프로토콜
- 연결 지향을 통해 신뢰성이 있는 통신을 제공

### 특징

- 3-way handshaking을 통해 연결
    - SYN 패킷을 통해 접속 요청
    - 요청을 수락하는 반대편이 ACK 와 SYN flag 설정된 패킷 발송
    - 요청했던 측이 ACK로 응답하면서 연결이 성사
- 4-way handshaking을 통해 연결 해제
    - 클라이언트가 연결 종료를 위해 FIN flag 전송
    - 서버가 확인 메세지로 ACK로 응답
    - 서버 측에서 통신이 끝나면 연결 종료로 FIN flag 전송
    - 클라이언트 측에서 ACK로 응답
- 흐름 제어
    - 데이터 처리 속도를 제어하여 수신자 버퍼 오버플로우 방지
- 혼잡 제어
    - 네트워크 패킷 수가 과도하게 증가하는 것을 제어
- 신뢰성 보장
- 전이중(Full-Duplex) - 전송이 양방향
- 점대점(Point to Potint) - 연결이 2개의 종착지를 가짐
- 1:1 통신만 지원
- UDP에 비해 속도가 느리다.

### 사용 예제

- FTP, telnet, SMTP, HTTP

## UDP(User Datagram Protocol)

### 개념

- 비연결형 프로토콜로 데이터그램 전송 방식

### 특징

- 데이터 수신 여부를 확인하지 않아 신뢰성이 떨어진다.
- TCP에 비해 속도가 빠르다.
- 일대일, 일대다, 다대다 통신이 가능하다.

### 사용 예제

- IP전화나 스트리밍 서비스 등에 사용

## Reference

[TCP와 UDP의 특징 및 차이점 알아보기](https://dev-coco.tistory.com/144)

[[ 네트워크 쉽게 이해하기 22편 ] TCP 3 Way-Handshake & 4 Way-Handshake](https://mindnet.tistory.com/entry/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-22%ED%8E%B8-TCP-3-WayHandshake-4-WayHandshake)