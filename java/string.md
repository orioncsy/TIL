# String

## 개념

### String class

- new 키워드를 통해 생성된 인스턴스의 메모리 공간은 불변(Immuntable)
- Garbage Collector로 제거
- 문자열을 연산할 때 새로운 객체를 생성하여 처리
- 객체 불변으로 멀티스레드 환경에서 안정함
- 문자열 연산이 적고 조회가 많은 멀티스레드 환경에 적합

### StringBuffer

- new 키워들 통해 생성하여 수정 가능(Mutable)
- 문자열 연산할 때 객체를 생성하지 않고 크기를 변경
- Thread-safe 하여 멀티 스레드 환경에서 사용 가능
- 문자열 연산이 많은 멀티스레드 환경에 적합

### StringBuilder

- new 키워들 통해 생성하여 수정 가능(Mutable)
- 문자열 연산할 때 객체를 생성하지 않고 크기를 변경
- Thread-safe 하지 않기 때문에 싱글 스레드 환경에서 사용 가능
- 문자열 연산이 많은 싱글스레드 환경에 적합

## Reference

[https://gyoogle.dev/blog/computer-language/Java/String%20&%20StringBuilder%20&%20StringBuffer.html](https://gyoogle.dev/blog/computer-language/Java/String%20&%20StringBuilder%20&%20StringBuffer.html)