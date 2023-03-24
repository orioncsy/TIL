# Concurrency Issue

## 개념

### 동시성 이슈

- 멀티 스레드 환경에서 공유 자원에 대한 접근으로 인해 발생하는 문제

## 해결 방법

### Synchronized

- synchronized 키워드가 붙은 메서드에는 하나의 스레드만 접근 가능
- 모든 공유 자원 가능성이 있는 영역에 synchronized 하는 것은 비현실적이고 성능도 저하된다.

### Atomic, Concurrent

- java.util.concurrent.*의 대표적인 클래스로 atomic과 concurrent가 존재
- volatile을 통해 메인 메모리에 있는 값을 바로 가져올 수 있다.
    - jvm에서는 cpu 메모리 영역에 데이터를 캐싱하는 값을 가져오는데 volatile을 사용하면 메인 메모리에서 바로 값을 가져와 최신의 데이터를 확인할 수 있다.
- CAS(Compare And Sweap) 알고리즘 사용
    - volatile 키워드를 사용하여 스레드에 저장된 값과 메인 메모리에 저장된 값을 비교
    - 일치하면 공유 자원에 접근하여 데이터를 변경
    - 일치하지 않으면 실패로 처리하고 재시도

## Reference

[https://devwithpug.github.io/java/java-thread-safe/](https://devwithpug.github.io/java/java-thread-safe/)