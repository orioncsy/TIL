# Null

# Null

## 개념

### Null

- Null 값을 갖는 변수는 JVM 메모리에서 값이 없으면 해시 코드를 0으로 가져 힙 영역에 데이터를 생성하지 않는다.
- 모든 멤버 타입은 Null 값을 가질 수 있고 사전에 처리하지 않으면 NPE(Null Pointer Exception)이 발생할 수 있다.

## Null을 다루는 방법

### equals()

- equals(null 객체)를 통해 객체가 null인지 확인할 수 있다.

### valueOf()

- null을 갖는 객체를 toString()을 사용하면 NPE가 발생할 수 있기 때문에 valueOf()를 통해 null을 반환할 수 있도록 한다.

### Null safe methods

- StringUtils 메서드가 대표적으로 null을 안전하게 처리할 수 있다.

### Null 반환 메서드 사용 절제

- Collections.EMPTY_LIST와 같이 비어있는 것을 표현하는 방식을 null을 반환하지 않도록 사용

### @NotNull, @Nullable

- 애너테이션을 활용하여 null값을 허용할지 아닐지 정하여 null을 처리할 수 있다.

### Autoboxing, autounboxing

- autoboxing이나 unboxing을 할 때 참조하는 객체가 null인 경우에는 NPE 발생하기 때문에 불필요한 사용을 지양

### Default 값을 설정

- NPE 발생을 예방하기 위해서 객체에 존재하는 멤버들을 null 값으로 설정되지 않도록 default 값을 설정

### DB null 제약 조건

- DB에 객체를 저장해야할 때 null 제약 조건을 정의
- DB 차원에서 null 값을 확인할 수 있기 때문에 java 코드에서 null check 감소

### Null Object Pattern

- 구현하고 싶은 인터페이스를 구현
- 인터페이스 내에 Boolean을 반환하는 isNull()이라는 메서드를 만들다.
- 해당 인터페이스의 구현체로 null 이 아닌 구현체는 isNull()을 false로 null인 구현체는 true로 재정의하고 용도에 맞게 구현체를 사용한다.

## Reference

[https://ddoyui.tistory.com/3](https://ddoyui.tistory.com/3)