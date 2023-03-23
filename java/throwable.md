# Throwable

## Error

### 개념

- Throwable 클래스를 상속받는 에러 클래스
- 시스템에 비정상적인 상황이 발생하였을 경우 에러 발생
- OutOfMemoryError 나 StackOverFlow와 같이 복구할 수 없는 경우

## Exception

### 개념

- Throwable 클래스를 상속받는 Exception 클래스
- 예외는 개발자의 실수로 발생하는 상황
- 심각하지 않아 프로그램을 복구할 수 없는 수준이 아닌 경우

### Checked Exception

- RuntimeException의 하위 클래스가 아닌 Exception 상속 클래스
- 컴파일 타임에서 확인할 수 있는 exception
- try catch로 예외처리를 강제한다.(컴파일 타임에서 처리가 되지 않으면 프로그램 실행이 불가하기 때문)
- 예외 발생 시 transaction에서 rollback하지 않는다.
- 예시
    - FileNotFoundException, ClassNotFoundException, IOException, SQlException

### Unchecked Exception

- RuntimeException의 하위 클래스
- 컴파일 타임에서 확인할 수 없는 exception
- try catch로 예외 처리를 강제하지 않는다.
- 예외 발생시 transaction에서 rollback한다.
- 예시
    - NullPointerException, IndexOutOfBoundException, IllegalArgumentException, SystemException

## Reference

[https://devlog-wjdrbs96.tistory.com/351](https://devlog-wjdrbs96.tistory.com/351)