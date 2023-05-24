# Singleton Pattern

## 개념

### Singleton Pattern

- 인스턴스를 1개만 생성하고 리턴하는 방식

  ![다이어그램 drawio](https://github.com/orioncsy/TIL/assets/90237119/641f2297-ff8f-40ac-a61c-fe15a744b198)


## 구현 방법

### 기본 구현 방식

```java
public class Singleton {
		private static Singleton instance;

    private Singleton() {}
 
    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
	        return instance;
    }
}
```

- 생성자를 private으로 두어 외부에서 new 키워드를 통해 생성할 수 없도록 한다.
- 객체를 필드 멤버로 두고 static 키워드를 둔다.
- getInstance() 메서드를 통해 instacne가 null일 경우에만 객체를 생성하고 반환한다.
- 멀티스레드 환경에서는 사용 불가

### Synchronized

```java
public class Singleton {
		private static Singleton instance;

    private Singleton() {}
 
    public static synchronized Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
	        return instance;
    }
}
```

- synchronized 키워드를 getInstance() 메서드에 붙여 동기화를 처리하여 멀티스레드 환경에서 사용 가능하게 한다.
- synchronized는 클래스 락이 걸려 다른 스레드가 클래스를 사용할 때 대기해야 해서 성능 문제 발생

### Eager initialization

```java
public class Singleton {
		private static Singleton instance = new Singleton();

    private Singleton() {}
 
    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
	        return instance;
    }
}
```

- synchronized를 사용하지 않고 instance 객체에 Singleton 객체를 new 키워드를 통해 초기화 시키는 방식
- 초기화를 먼저하기 때문에 생성하는데 많은 비용이 소모될 수 있다.

### Double Checked Locking

```java
public class Singleton {
		private static volatile Singleton instance;

    private Singleton() {}
 
    public static Singleton getInstance() {
        if (instance == null) {
            synchronized (Singleton.class) {
                if(instance==null){
                    instance = new Singleton();
                }
            }
        }
        return instance;
    }
}
```

- lock을 통한 성능 악화를 개선하기 위해 instance가 null인지 확인하고 synchronized를 사용하여 동기화 처리 후에 다시 instance가 null인지 확인하는 방식
- instance를 volatile로 선언하여 메모리에 접근하여 데이터를 가져오게 한다.
- volatile 키워드를 반드시 사용해야 하는 이유는 메모리에 바로 접근하지 않으면 다른 스레드에서 cpu 캐시에만 변수값이 머무르기 때문에 동기화처리가 제대로 이루어 지지 않는다.

### Lazy initialization(Singleton Holder Pattern)

```java
public class Singleton(){
	private Singleton(){}
	
	private static class SingletonHolder{
		private static final Singleton INSTANCE = new Singleton();
	}

	public static Singleton getInstance(){
		return SingletonHolder.INSTANCE;
		
	}
}
```

- static inner class를 사용해 singletonHolder 클래스를 생성하고 static으로 올라올때 초기화를 시켜 사용하는 방식

### enum

```java
enum Singleton{
	INSTANCE
}
```

- enum은 상속이 불가능하고, 초기 생성 비용이 크다.

### 싱글톤 깨는 방식

- 직렬화 또는 역직렬화하거나 리플렉션을 통해 enum 싱글톤을 제외하고 깨질 수 있다.
- 리플렉션은 클래스 타입은 몰라도 메서드, 변수 등에 접근할 수 있도록하는 자바 API로 생성자에 접근해 새로운 객체를 따로 생성 가능할 수 있다.

## Reference

https://effortguy.tistory.com/183