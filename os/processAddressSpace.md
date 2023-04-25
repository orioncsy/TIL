# Process Address Space

## 개념

### Process Addresss Space

- 프로그램이 실행되면 주소공간이 memory에 할당
- 할당된 process를 CPU가 실행

## 구성

### Code Segment(코드 부분)

- 프로그램 코드가 저장
- 읽기만 가능

### Data Segment(데이터 부분)

- 전역 변수 같은 데이터를 저장
- 읽고 쓰기 가능

### Stack Segment(스택 부분)

- 함수나 지역 변수 저장
- 읽고 쓰기 가능

## 공간 분리 목적

### 코드 부분

- 프로그램 코드는 변경되면 안 되기 때문에 따로 관리

### 데이터 부분과 스택 부분

- 전역변수는 어떤 함수도 접근 가능하기 때문에 데이터 부분으로 따로 관리
- 스택 부분은 구조에 따라 LIFO 방식으로 구현

## Reference

[https://whereisusb.tistory.com/10](https://whereisusb.tistory.com/10)