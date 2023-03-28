# Annotation

## 개념

### 의미

- 자바 소스코드에 추가하여 사용할 수 있는 일종의 메타 데이터
- @ 기호를 붙여 사용
- jdk 1.5 이상에서 사용 가능
- 클래스 파일에 임베디드되어 컴파일러에 의해 생성된 후 자바 가상머신에 포함되어 작동

## 종류

### 표준 어노테이션

- @Override
    - 오버라이딩할 때 사용
- @Deprecated
    - 사용하지 않을 것을 권장
- @FunctionalInterface
    - 함수형 인터페이스에 사용
- @SuppressWarnings
    - 컴파일러의 경고를 표시하지 않을 때 사용

### 메타 어노테이션

- 어노테이션에 대한 정보를 제공하는 어노테이션
- @Target
    - 적용 대상 지정
- @Retention
    - 유지 기간
    - SOURCE, RUNTIME 등
- @Documented
    - javadoc 문서에 포함하기 위한 어노테이션
- @Inherited
    - 어노테이션 상속
- @Repeatable
    - 여러 개 적용할 수 있도록하는 어노테이션

## 어노테이션 생성

### 생성 방법

- @interface 이름{}을 통해 선언

### 어노테이션 요소 특징

- default를 사용하여 기본값 지정 가능
- 요소가 하나이고 이름이 value 인 경우에는 요소 이름 생략 가능
- 요소 타입이 배열인 경우 괄호{} 사용

## 어노테이션 조상

### Annotation

- 모든 어노테이션의 조상이지만 상속 불가

## 마커 어노테이션

### 요소가 하나도 정의되어 있지 않은 어노테이션

- @Test 처럼 테스트 프로그램에게 테스트 대상을 알리는 역할을 하는 경우가 해당된다.

## 어노테이션 규칙

### 요소 타입

- 기본형, String, enum, 어노테이션, class만 허용

### () 안에 매개변수 선언불가

- String fun(int i) 처럼 선언 불가

### 예외 선언 불가

- throw Exception 선언 불가

### 요소타입 매개변수로 정의 불가

- ArrayList<T> list(); 처럼 정의 불가

## Reference

[https://velog.io/@jkijki12/annotation](https://velog.io/@jkijki12/annotation)