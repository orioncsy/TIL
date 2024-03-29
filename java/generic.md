# Generic

## 개념

### Generic

- 타입을 일반화
- 클래스 내부에서 타입을 정하는 것이 아니라 외부에서 직접 지정하여 컴파일 타임에서 검사
- 특정 타입의 변수형이 지정되지 않고 설정 가능

### 제너릭 타입(Generic Type)

- 타입을 파라미터로 갖는 클래스나 인터페이스
- 클래스나 인터페이스 뒤에 꺽쇠(<>)를 사용하고 그 안에 타입 파라미터를 작성해서 사용
- 특정 파라미터에 종속되지 않는다.

### 타입 파라미터

- 제너릭 타입에 사용하는 매개변수로 정해지지 않은 파라미터
- 참조 타입은 T(Type), 요소는 E(Element), 키는 K(Key), 값은 V(Value)로 표시

## 사용 목적

### 재사용성 증가

- 여러 타입 파라미터를 사용해 코드를 간결하고 재사용을 높게 해 준다.
- 동일한 기능을 하는 메서드에서 타입 파라미터를 다르게 하면 오버로딩보다 활용성이 높다.

### 컴파일 타임에서 타입 에러 검출

- 잘못 사용된 타입을 컴파일 타임에서 검출이 가능하여 런타임에서 문제 발생을 방지할 수 있다.

### 컴파일러가 타입 변환 수행

- 컴파일 단계에서 컴파일러가 타입 변환을 해주기 때문에 코드에서 형변환하는 수고를 덜 수 있다.

## 사용 방식

### 제너릭 클래스

- class Student <T>{…}

### 제너릭 인터페이스

- interface Student <T>{…}

### 제너릭 타입 상속

- 부모 클래스나 인터페이스를 상속받을 때 타입 파라미터에 부모 클래스나 인터페이스 타입 파라미터를 먼저 작성해 준다.

## Reference

[https://life-with-coding.tistory.com/489](https://life-with-coding.tistory.com/489)