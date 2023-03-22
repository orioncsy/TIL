# Static

## 개념

### static 키워드

- 변수와 메서드 앞에 붙여 정적 필드, 정적 메서드로 사용 가능
- 정적 필드, 정적 메서드를 합쳐서 클래스 멤버라 부른다.

### 특징

- 클래스 로더가 메서드 영역에 클래스를 로드할 때 클래스별로 관리
- 클래스 로딩이 끝나면 즉시 사용 가능
    - static 메서드의 경우 객체 선언하지 않아도 사용 가능
- 정적 멤버들은 static 영역에 할당되기 때문에 GC가 활동하는 heap 영역이므로 프로그램 종료 시까지 메모리에 잔존
- static을 남발하면 시스템에 악영향을 줄 수 있다.

## Reference

[https://coding-factory.tistory.com/524](https://coding-factory.tistory.com/524)