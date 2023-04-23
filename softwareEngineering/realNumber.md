# Real Number

## 개념

### 실수 표현 방법

- 컴퓨터에서 실수를 표현하는 방법은 2가지 존재
- 고정 소수점, 부동 소수점

## 고정 소수점

### 개념

- 소수점이 찍힐 곳을 정해놓고 정수부와 소수부를 나누어 표현

### 표현 방식

- 32bit로 표현한다면 1bit는 부호를 결정하고 15bit는 정수부, 16bit는 소수부로 표현

### 장단점

- 단순하게 표현할 수 있지만 표현 범위가 제한적이다.

## 부동 소수점

### 개념

- 소수점이 찍힐 위치가 정해지지 않고 유동적인 방식

### 표현 방식

- IEEE 표현 방식에 따라 single precision(32bit)과 double precision(64bit)으로 구분
- 32bit는 1bit 부호, 8bit 지수부(exponent), 23bit 가수부(mentissa)
- 64bit는 1bit 부호, 11bit 지수부(exponent), 52bit 가수부(mentissa)
- 지수부에는 소수점의 위치를 지수로 표현하고 bias(2^(k-1)-1, k는 지수부 bit 수)를 합하여 표현
- 가수부는 앞에 1만 남기고 이후 소수점 아래의 수들을 저장

### bias 표현법

- bias를 더해 지수로 표현하는 이유는 지수는 음수여도 값 자체는 양수이기 때문에 지수가 음수일 경우를 표현하기 위해 사용

### 장단점

- 표현할 수 있는 값의 범위가 상대적으로 넓지만 오차 발생 가능

## Reference

[https://thrillfighter.tistory.com/349](https://thrillfighter.tistory.com/349)

[https://gyoogle.dev/blog/computer-science/computer-architecture/%EA%B3%A0%EC%A0%95%20%EC%86%8C%EC%88%98%EC%A0%90%20&%20%EB%B6%80%EB%8F%99%20%EC%86%8C%EC%88%98%EC%A0%90.html](https://gyoogle.dev/blog/computer-science/computer-architecture/%EA%B3%A0%EC%A0%95%20%EC%86%8C%EC%88%98%EC%A0%90%20&%20%EB%B6%80%EB%8F%99%20%EC%86%8C%EC%88%98%EC%A0%90.html)