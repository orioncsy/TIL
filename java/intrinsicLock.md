# 고유락

## 개념

### 고유 락

- Java의 모든 객체는 각자 고유한 lock을 가지고 있다.
- synchronized 블록은 고유 락을 통해 스레드 접근 제한

### Synchronized 블록

- synchronized(객체){ … } 를 통해 블록 생성 가능
- public synchronized int 처럼 접근제어자 뒤에 붙여 객체를 생성할 필요 없이 블록 생성 가능

### 재진입 가능성(Reentrancy)

- lock을 획득한 thread가 lock을 얻기 위해 대기할 필요가 없는 상태
- lock을 획득하는 것은 호출 단위가 아니라 스레드 단위이다.
- 하나의 스레드가 synchronized로 선언된 메서드에 접근하고 그 안에 또 다른 synchronized로 선언된 메서드를 호출하는 상황에서 스레드가 lock을 가지고 있기 때문에 호출이 가능

## 종류

### Structured Lock

- 고유 lock을 통한 동기화를 구조적인 lock이라고 한다.
- synchronized 블록으로 구현

### Reentrant Lock

- 명시적인 lock으로 Reentrant lock 객체를 생성하여 lock을 직접적으로 지정할 수 있다.

## 가시성

### 개념

- 동시성 프로그램 이슈 중의 하나로 가시성 문제가 존재
- 하나의 스레드가 쓴 값을 다른 스레드가 볼 수도 있고 아닐 수도 있다면 가시성 문제가 발생
    - 하나의 스레드가 값을 쓸 때 원자적 연산이 아닌 경우에는 다른 스레드가 도중에 값을 가져오면 dirty read가 되기 때문에 문제 발생
    - 원자적 연산이란 하나의 작업으로 이루어지는 경우를 의미
    - count++ 처럼 값을 읽고 수정하고 다시 값을 저장하는 3가지 작업이 이루어져 여러 thread가 공유 자원으로 접근하는 경우는 원자적 연산이 아니다.
- lock을 사용하면 동시성 문제를 해결할 수 있다.

## Reference

[http://happinessoncode.com/2017/10/04/java-intrinsic-lock/](http://happinessoncode.com/2017/10/04/java-intrinsic-lock/)

[https://gyoogle.dev/blog/computer-language/Java/Intrinsic%20Lock.html](https://gyoogle.dev/blog/computer-language/Java/Intrinsic%20Lock.html)