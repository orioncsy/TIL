# Record

## 개념

### record

- java 14부터 도입되어 16 버전부터 정식 스펙에 포함된 record는 class처럼 타입으로 사용 가능
- 순수한 데이터를 보유하기 위한 클래스

## 사용 방식

### 기존 사용 방식

- 일반적으로 class로 객체를 선언하고 필드를 입력하고 생성자, getter를 구현한다.

### record 사용 방식

- public record 키워드로 클래스를 선언하면 자동으로 필드를 private final로 생성하고 생성자와 getter를 자동으로 생성한다.
- getter 메서드의 경우 일반적으로 선언하는 get000() 식의 네이밍이 아니라 000() 형태로 선언한다.

## Reference

[https://gyoogle.dev/blog/computer-language/Java/Record.html](https://gyoogle.dev/blog/computer-language/Java/Record.html)