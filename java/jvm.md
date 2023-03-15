# JVM

## 개념

### JVM(Java Virtual Machine)

- 자바 소스 코드로부터 컴파일된 바이트 코드를 실행하는 역할

### JRE(Java Runtime Environment)

- JVM을 포함하고 JVM이 바이트 코드를 실행하기 위한 라이브러리 파일 및 기타 파일을 가지고 실행 환경을 구성

### JDK(Java Development Kit)

- JRE를 포함하고 개발을 위해 필요한 도구들을 제공

## JVM 구성

### Class loader

- 런타임 시 클래스 파일들을 JVM 내부로 로딩하고 파일을 분석하여 Runtime data area에 배치
- 자바는 동적으로 클래스를 읽어오기 때문에 런타임 시점에 모든 코드가 JVM에 올라온다.

### Runtime Data Areas

- class loader로부터 분석된 클래스 파일들과 실행 도중 필요한 데이터를 저장
- 메모리를 5개의 영역으로 구분하여 메모리 영역이라고도 부른다.

### Execution Engine

- runtime data area에 배치된 바이트 코드를 해석하고 실행
- 인터프리터와 JIT 컴파일러를 혼합해서 사용
- 인터프리터
    - 바이트 코드를 한 줄씩 읽고 해석
- JIT 컴파일러(Just In Time)
    - 바이트 코드를 런타임 시점에 바로 기계어로 변환
- 최초의 가상머신은 인터프리터만 사용하여 속도가 느렸지만 JIT 컴파일러를 사용하여 개선
- JIT 컴파일러는 기계어로 바꾸는데 비용이 발생하기 때문에 인터프리터를 사용하다 일정 수준이 넘어가면 JIT를 사용하는 혼합 방식을 사용

### Garbage Collector

- runtime data area에 있는 heap의 데이터들 중에 사용하지 않는 데이터를 제거하는 작업

## JVM 구동 방식

1. .java로 된 소스코드를 작성
2. 자바 컴파일러(javac.exe)를 통해 바이트 코드(.class)로 변환
3. 런처(java.exe)를 통해 JVM을 구동
4. class loader가 클래스를 runtime data area에 올린다.
5. excution engine이 작동하면서 자바 프로그램이 실행

## JVM 메모리 영역

### Method

- 데이터가 가장 먼저 저장되는 공간
- 클래스, 인터페이스, 메서드, static(클래스 변수), 전역 변수 등이 저장
- 프로그램 시작부터 종료까지 메모리에 남는다.
- 명시적인 null 선언하면 GC 대상
- 모든 스레드가 공유

### Heap

- 런타임 시 결정되는 참조형 데이터 타입(기본 타입을 제외한 자료형)이 저장되는 공간
- new 키워드 연산자를 사용하여 객체가 저장되는 공간
- 객체가 더 이상 쓰이지 않거나 명시적 null을 선언하면 GC 대상
- 모든 스레드가 공유

### Stack

- 컴파일 시 결정되는 기본형 데이터 타입이 저장되는 메모리
- 지역변수, 매개변수, 리턴값, 참조 변수, 임시적인 데이터를 저장
- 메서드가 호출될 때 FILO, 메서드가 종료될 때 LIFO 방식으로 처리
- 메서드 호출 시 마다 각각 스택프레임이 생성
- 메서드가 끝날 때까지만 메모리에 유지

### PC Register

- JVM이 실행할 명령어 주소를 저장하는 공간
- 스레드가 시작될 때마다 생성

### Native method stack

- 바이트 코드가 아닌 기계어로 작성된 코드를 실행하는 공간
- 다른 언어로 작성된 코드 실행
- Java Native Interface를 통해 바이트 코드로 변환

## Reference

[https://gbsb.tistory.com/2](https://gbsb.tistory.com/2)