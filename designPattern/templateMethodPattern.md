# Template Method Pattern

## 개념

### Template Method Pattern

- 로직을 단계별로 구변할 때 사용하는 설계 패턴
- 특정 단계가 수정될 가능성이 있는 경우 효율적이다.

## 구현 방식

### 기본 조건

![다이어그램 drawio](https://github.com/orioncsy/TIL/assets/90237119/d354f485-22bc-49fa-8461-f470663236cf)

- 추상 클래스로 구현한다.
- 단계를 진행하는 메서드는 final을 통해 수정을 못하도록 제한한다.
- 각 단계는 외부에서 접근 못하게 하고 자식 클래스만 수정하도록 허용하기 위해 protected로 선언한다.

## 구현 사례

### 추상 클래스

```java
abstract class Pasta{
	protected void boil(){ System.out.println("Boil noodles"); }
	abstract void sauce(){}
	protected void fry(){ System.out.println("fry pasta"); }

	final void cookPasta(){
		this.boil();
		this.sauce();
		this.fry();
	}
} 
```

### 하위 클래스

```java
class AglioOlio extends Pasta{
	@Override
	void sauce(){ System.out.println("pour garlic & olive oil"); }
}

class Carbonara extends Pasta{
	@Override
	void sauce(){ System.out.println("pour yolk & cheese"); }
}

class Pomodoro extends Pasta{
	@Override
	void sauce(){ System.out.println("pour tomato & bazil"); }
}
```

## Reference

https://gyoogle.dev/blog/design-pattern/Template%20Method%20Pattern.html