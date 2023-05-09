
# Serialization

## 개념

### 직렬화

- 자바 시스템에서 사용하는 객체나 데이터를 외부의 자바 시스템에서 사용할 수 있도록 바이트 형태로 변환하는 기술
- 각자의 PC의 운영체제에서는 다른 가상 메모리 주소를 사용하기 때문에 참조 타입의 인스턴스는 전달할 수 없다.
- 이러한 문제를 해결하기 위해 주소값을 바이트 형태로 변환하여 데이터를 전달할 필요가 존재
- 직렬화된 데이터는 원시 타입으로 변환되고 파일 저장이나 전송할 때 유의미한 데이터가 된다. 이 과정을 직렬화이다.

### 역직렬화

- 직렬화를 통해 변환된 바이트 데이터를 다시 자바 객체나 데이터 형태로 변환하는 기법

## 직렬화 조건

### 구현 방식

- java.io.serializable 인터페이스를 구현으로 직렬화, 역직렬화가 가능

### 대상

- 인터페이스를 구현한 구현체, 원시 타입 데이터
- 참조 타입처럼 주소 값을 가지고 있다면 인터페이스를 구현해야 한다.

### 상황

- JVM에 존재하는 데이터를 영속화할 때 사용
- Servlet session
    - 일정 시간 동안 같은 사용자로부터 들어오는 일련의 요구를 하나의 상태로 보고 유지하는 기술이 session
- Cache
- Java RMI(Remote Method Invocation)
    - 분산되어 존재하는 객체 간의 메시지 전송을 가능하게 하는 프로토콜

## 구현

### 직렬화

- ByteArrayOutputStream 객체를 생성하고 ObjectOutputStream 객체를 생성할 때 넘겨준다.
- ObjectOutputStream 객체에 writeObject() 메서드에 객체를 인자에 전달한다.
- ByteArrayOutputStream 객체에 toByteArray() 메서드를 통해 바이트 배열 형태로 저장한다.

### 역직렬화

- ByteArrayInputStream 객체를 생성하고 생성 인자에 바이트 배열 데이터를 전달한다.
- ObjectInputStream 객체를 생성할 때 ByteArrayInputStream 객체를 넘겨준다.
- ObjectInputStream의 readObject() 메서드를 사용하여 Object 형태로 저장
- 형변환을 통해 객체에 저장한다.

## SerialVersionUID

### 개발자 관리

- serialVersionUID는 자동으로 해시값이 설정된다.
- 그러나 맴버 변수가 변경되면 serialVersionUID도 변경된다.
- 직접 관리를 해야 serialVersionUID가 변경되어 예외가 발생하는 것을 예방할 수 있다.

## Reference

[https://gyoogle.dev/blog/computer-language/Java/Serialization.html](https://gyoogle.dev/blog/computer-language/Java/Serialization.html)