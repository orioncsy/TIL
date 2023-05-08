# Object Class

## 개념

### Object Class

- Java의 최상위 클래스
- Object Class의 메서드를 오버라이딩하여 사용 가능

## 주요 메서드

### toString()

- 객체의 해시코드를 출력
- 클래스풀네임@해시코드 형태의 문자열을 출력
- 오버라이딩하여 객체 정보를 문자열로 표현할 때 주로 사용

### equals()

- 기본적으로는 == 연산 결과를 반환(동일성을 비교)
- 오버라이딩하여 다른 주소값을 가지는 객체의 동등성을 비교(객체 내용을 비교)

### hashCode()

- JVM이 인스턴스를 생성할 때 메모리 주소를 변환하여 부여한 코드
- 실제 메모리 값과는 별개
- 오버라이딩하여 주소값은 다르지만 객체 내용이 동등한 경우 동일성을 가지도록 하기 위해 사용
- HashSet이나 HashMap의 경우에는 객체를 저장하기 위해 hashCode를 이용한다.
    - hashSet과 같은 경우 두 객체의 주소가 다르게 생성을 하고 같은 내용을 담는다면 hashSet에서는 주소가 다르기 때문에 2개의 객체를 저장한다. 만약 hashCode()를 오버라이딩한다면 해당 객체들을 같은 객체로 인식하고 하나만 저장한다.
- eqauls()가 오버라이딩되면 hashCode() 또한 오버라이딩되어야 한다.

### clone()

- 객체의 복사본을 생성
- 정보 은닉에 위배될 수 있기 때문에 복제할 객체는 Cloneable 인터페이스를 명시해야 한다.

### finalize()

- 직접 호출하는 것이 아니라 GC가 메모리 해제할 때 사용하는 메서드

## Reference

[https://mangkyu.tistory.com/101](https://mangkyu.tistory.com/101)

[https://atoz-develop.tistory.com/entry/자바-Object-클래스-정리-toString-equals-hashCode-clone](https://atoz-develop.tistory.com/entry/%EC%9E%90%EB%B0%94-Object-%ED%81%B4%EB%9E%98%EC%8A%A4-%EC%A0%95%EB%A6%AC-toString-equals-hashCode-clone)