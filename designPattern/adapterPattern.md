# Adapter Pattern

## 개념

### Adapter Pattern

- 어떤 클래스의 인터페이스를 다른 인터페이스로 변환하여 사용하는 설계 방식
- Adapter를 이용하여 인터페이스 호환성 문제를 해결

### 특징 및 장점

- 호환되지 않는 인터페이스를 사용 가능하게 한다.
- 클라이언트와 인터페이스를 분리하여 인터페이스가 변경되어도 adapter에 캡슐화되어 클라이언트 수정이 필요 없다.

### 다이어그램

![다이어그램 drawio](https://github.com/orioncsy/TIL/assets/90237119/c55674b0-3e2f-408a-967e-c281ca192a9a)

- 기존 시스템에서 Target 인터페이스를 사용하고 adaptee 인터페이스를 사용하고자 하는 상황
- 변환하고자 하는 대상 인터페이스는 adaptee
- 변환을 해서 이루고자 하는 형태의 인터페이스는 target

## Adapter 구현 방식

### 클래스 어댑터

- 다중 상속을 통해 Target과 Adaptee를 모두를 상속하여 구현
- 자바에서는 다중 상속이 불가능하기 때문에 사용하기 어렵다.

### 객체 어댑터

- Target을 구현하는 Adapter 클래스를 구성하고 필드 맴버로 Adaptee 인스턴스를 담아 구현

## 예시

### 상황

- 110v를 사용하는 일본 플러그를 한국에서 어댑터를 끼워 220v로 변환하려는 상황
- target은 한국 220v 플러그
- adaptee는 일본 110v 플러그

### Target

```java
public interface Plug220 {

          public void 220v();
          public void power();

 }

public class KoreanPlug implements Plug220 {

          @Override
          public void 220v() {
                   System.out.println("by 220v");
          }
          
          @Override
          public void power() {
                   System.out.println("power");
          }

}
```

### Adaptee

```java
public interface Plug110 {

          public void 110v();
          public void power();

 }

public class JapanesePlug implements Plug110 {

          @Override
          public void 110v() {
                   System.out.println("by 110v");
          }
          
          @Override
          public void power() {
                   System.out.println("power");
          }

}
```

### Adapter

```java
public class Plug110Adapter implements Plug220 {

          Plug110 plug110;

          public Plug110Adapter(Plug110 plug110) {
                   this.plug110= plug110;
          }

          @Override
          public void 220v(){ 
                   plug110.110v();
          }

          @Override
          public void power() {
                   plug110.power();
          }

 }
```

## Reference

[https://jusungpark.tistory.com/22](https://jusungpark.tistory.com/22)