# JDK 변화

## JDK 버전별 변화

### JDK 5

- generic
    - 외부에서 타입을 지정해 주는 방식
    - 제너릭을 사용해 classCastException을 컴파일 타임에서 확인 가능
- for each 가능
- concurrent API
    - 멀티 스레드를 쉽게 구현 가능
- 어노테이션 사용 가능
- enum 사용 가능
- autoboxing / auto unboxing
    - 기본 자료형을 래퍼 클래스로 자동 변환

### JDK 6

- G1 GC
    - 1MB 크기의 영역을 구분해서 관리
    - 자바 7부터 기본 GC로 채택
- desktop API
- 자바 컴파일러 API
    - 자바 코드에서 직접 컴파일러를 호출 가능

### JDK 7

- FILE NIO 2.0
    - 파일 처리를 위한 기능 제공
- 포크/조인 프레임 워크
    - concurrent API에 포크, 조인 기능 추가
    - 멀티 스레드 생성과 더불어 라이프 사이클 관리 가능
- 다이아몬드 연산자
    - 제너릭을 더 쉽게 사용하기 위해서 <> 연산자를 사용
- try-with-resource
    - try 블록에 자원을 전달하고 블록이 끝나면 자원을 자동으로 종료

### JDK 8

- 람다 표현식
    - 별도의 익명 클래스를 만들어 선언하지 않고 간편하게 표현
- 함수형 인터페이스
    - 하나의 메서드를 가지는 인터페이스로 람다식을 사용할 때 주로 사용
- 메서드 참조
    - 특정 메서드를 메서드 인수에 전달 가능
- 스트림 API
    - 병렬처리, 스트림 파이프라인을 통해 하나의 문장으로 다양한 처리 가능
- 날짜, 시간 API
    - 기존 Date, Calendar 클래스의 문제점을 개선하기 위해 추가
- Optional
    - optional 클래스를 통해 nullPointerException을 예방
- 인터페이스 개선
    - default 키워드를 이용해서 인터페이스에 메서드를 추가하고 내용을 작성 가능
- CompletableFuture
    - 기존 future 인터페이스에서 기능 개선

### JDK 9

- 리액티브 프로그래밍
    - 병렬 실행 기법

### JDK 11

- HTTP 클라이언트
    - HTTP 클라이언트 API를 정식으로 포함
    - URLConnection 기반 HTTP 개발보다 개선된 기능
    - HTTP 2.0을 지원해 웹 소켓 기능 포함
- 컬렉션 객체를 배열로 변환
    - 컬렉션 인터페이스에 ToArray 메서드 추가
- var 키워드 지원 확대
    - var 키워드로 변수를 선언하면 자동으로 타입을 추론하는 기능
    - 자바 11에서는 람다식 표현에서 사용 가능
- String 클래스 기능 추가
    - isBlank을 통한 공백 확인
    - 문자열을 스트림 api 객체로 생성하는 lines
    - 공백을 지우는 strip, stripLeading, stripTrailing 추가

## Reference

[https://truehong.tistory.com/114](https://truehong.tistory.com/114)