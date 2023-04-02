# Wrapper Class

## Wrapper Class

### 개념

- 기본 타입의 데이터를 객체로 취급해야 하는 경우 객체형태로 포장하는 클래스를 의미
- Byte, Short, Integer, Long, Float, Double, Character, Boolean
- 래퍼 클래스는 산술을 위해 정의된 클래스가 아니라서 인스턴스에 저장된 값을 변경 불가

### 비교

- wrapper class는 객체이기 때문에 동등성을 비교할 때 equals 메서드를 사용하여 비교할 수 있다.

## Boxing & UnBoxing

### Boxing

- 기본 타입의 데이터를 wrapper class로 변환

### Unboxing

- wrapper class를 기본 타입의 데이터로 변환

## AutoBoxing & AutoUnBoxing

- boxing과 unboxing을 자바 컴파일러에서 자동으로 처리

### 성능

- 다른 타입을 연산하게 되면 추가 연산 작업이 필요하기 때문에 같은 타입에 비해 성능이 떨어진다.

## Reference

[http://www.tcpschool.com/java/java_api_wrapper](http://www.tcpschool.com/java/java_api_wrapper)