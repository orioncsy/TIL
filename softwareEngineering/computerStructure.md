# Computer Structure

## 개념

### 컴퓨터 구성

- 하드웨어
    - 컴퓨터를 구성하는 물리적인 장치
    - 중앙처리장치(CPU), 기억장치, 입출력 장치
- 소프트웨어
    - 컴퓨터를 동작시키는 명령의 집합
    - 시스템소프트웨어(OS, compiler), 응용소프트웨어(워드, 한글)

## 하드웨어

### 중앙처리장치(CPU)

- 주기억장치에서 명령과 데이터를 가져와 연산을 처리하는 역할
- 비교 및 연산을 하는 산술논리연산장치
- 명령어 해석 및 실행을 하는 제어장치
- 용량은 적고 속도는 빠른 기억장치인 레지스터

### 기억장치

- 데이터를 저장하는 장치
- 주기억장치
    - RAM, ROM 등이 해당
    - 프로그램에 필요한 데이터를 임시로 저장
    - 휘발성 메모리
- 보조기억장치
    - 하드디스크나 SSD 등이 해당
    - 주기억장치에 비해 속도는 느리지만 영구적으로 데이터를 저장할 때 사용

### 입출력장치

- 입력 장치
    - 데이터를 입력하는 장치로 키보드, 마우스가 해당
- 출력 장치
    - 데이터를 출력하는 장치로 모니터, 스피커가 해당

## 시스텀 버스

- 하드웨어 구성요소들을 연결하는 선

### 데이터 버스

- CPU와 다른 장치들로 데이터를 전달할 때 연결하는 버스
- 양방향 버스로 작동

### 주소 버스

- 데이터를 전달할 기억 장치 주소를 전달할 때 연결하는 버스
- CPU에서 주기억장치나 입출력 장치로 주소값을 전달만 해주기 때문에 단방향 버스

### 제어 버스

- CPU가 데이터를 전송하거나 상태를 전달하기 위해 신호를 보내는 버스
- 기억장치 동기 신호, 데이터 전송, 주소 신호, 상태 신호, 입출력 동기 신호, 중앙처리 장치 동기 신호 등의 신호 존재

## Reference

[http://terms.tta.or.kr/dictionary/dictionaryView.do?subject=제어+버스](http://terms.tta.or.kr/dictionary/dictionaryView.do?subject=%EC%A0%9C%EC%96%B4+%EB%B2%84%EC%8A%A4)