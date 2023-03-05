# Garbage Collector

## GC

### 개념

- JVM에서 유효하지 않은 메모리를 정리하는 역할
- 자바에서는 직접 메모리를 해제할 수 없기 때문에 GC를 사용

## JVM HEAP

- JVM에서 heap 영역에는 초기에 크게 2가지 영역으로 구분

### Young 역역

- 새롭게 형성되는 객체가 할당된다.
- 주로 자주 사용하고 버려지는 일회성 데이터가 저장되는 곳으로 크기가 작다.
- 크기가 작은 만큼 GC 실행 시간이 짧다. 이러한 이유로 이곳에서 실행되는 GC를 Minor GC로 표현
- young에는 다시 eden, survivor0, survivor1이 존재한다.
    - GC를 실행해서 살아남은 데이터가 다음 영역으로 넘어간다.

### Old 영역

- young 영역에서 GC를 실행하여 살아남은 데이터가 복사되는 곳이다.
- 데이터가 크거나 오랫동안 살아남은 데이터가 존재하여 크기가 크고 GC는 적게 발생된다.
    - 이러한 이유로 old영역에서 실행되는 GC를 Major GC로 표현

### Card table

- 예외적으로 old 영역의 객체가 young 영역의 객체를 참조하는 경우를 대비해 old 영역에 512 Bytes 덩어리로 된 테이블 존재
- 카드 테이블에 old 영역이 young 영역을 참조하는 경우 정보를 저장
- young 영역에서 GC를 실행할 때 모든 old 영역을 검사하면 비효율적이라서 카드테이블을 참조하여 GC 대상인지 판별

## 동작 방식

### Stop The World

- GC를 실행하는 스레드를 제외한 모든 애플리케이션 실행을 정지하는 과정

### Mark and Sweep

- 참조할 수 있는 메모리를 mark하고 mark 되지 않은 메모리를 제거하는 sweep 과정

## GC 종류

### Serial GC

- minor GC의 경우 STW와 mark and sweep이 실행되고 major GC의 경우 compact 알고리즘 추가 실행
- compact는 사용하고 있는 메모리의 빈 공간을 채우는 알고리즘
- 단일 스레드로 동작

### parallel GC

- serial GC를 멀티 스레드를 사용하여 병렬로 처리

### CMS(Concurrent Mark and Sweep) GC

- parallel GC처럼 멀티 스레드로 동작하지만 여러 번 나뉘어서 GC 실행
- 초반에 STW를 통해 GC를 실행하여 mark를 진행하고 다시 애플리케이션을 구동
- 애플리케이션 구동 도중에 다시 GC를 실행하여 mark를 진행
- 다시 STW를 통해 애플리케이션을 멈추고 새로 참조된 메모리를 mark 하고 sweep

### G1(Garbage first) GC

- java 9 버전 이후부터 기본 GC로 채택
- 물리적으로 young, old 영역을 나누지 않고 region을 통해 힙 메모리를 균등하게 나누어 관리
- 가비지가 많은 region 부터 GC 실행
- 각 지역을 eden, survivor, old인지 논리적으로 구분
- humongous(region 크기 50% 이상 객체를 저장하는 영역), available/unused(사용되지 않은 region) 존재
- old GC의 경우 concurrent 방식으로 GC 진행

## Reference

[https://mangkyu.tistory.com/118](https://mangkyu.tistory.com/118)

[https://mangkyu.tistory.com/119](https://mangkyu.tistory.com/119)