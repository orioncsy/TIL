# Factory Method Pattern

## 개념

### Factory Method Pattern

- 생성 패턴 중에 객체를 생성하는 부분을 서브 클래스에 맡기는 패턴

![다이어그램 drawio (1)](https://github.com/orioncsy/TIL/assets/90237119/34388e01-a903-4ad6-a7ae-5aa7933e6c3e)

## 구현 사례

### Creator

```java
public abstract class ChickenFactory{
    abstract Chicken createChicken();
}
```

### ConcreteCrator

```java
public class FriedChickenFactory extends ChickenFactory{
    @Override
    Chicken createChicken(){
        return new FriedChicken();
    }
}

public class SeasonedChickenFactory extends ChickenFactory{
    @Override
    Chicken createChicken(){
        return new SeasonedChicken();
    }
}
```

### Product

```java
public abstract class Chicken(){
    abstract void taste();
}
```

### ConcreteProduct

```java
public class FriedChicken extends Chicken{
    @Override
    public void taste(){
        System.out.println("taste like FriedChicken!!");
    }
}

public class SeasonedChicken extends Chicken{
    @Override
    public void taste(){
        System.out.println("taste like SeasonedChicken!!");
    }
}
```

## 장단점

### 장점

- 객체 생성을 하나의 한 곳에서 관리 가능
- 새로운 객체가 추가되더라도 기존 코드 수정이 거의 없다.

### 단점

- 패턴 구현을 통하여 코드가 복잡해지고 코드 길이가 길어질 수 있다.

## Reference

https://gyoogle.dev/blog/design-pattern/Factory%20Method%20Pattern.html