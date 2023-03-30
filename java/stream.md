# Stream

## 개념

### Collection과 Stream 차이

- Collection은 모든 값을 메모리에 저장하는 자료 구조로 Collection에 추가하기 전에 계산이 완료되어 있어야 한다.
    - 외부 반복을 통해 사용자가 직접 반복 작업을 거쳐 요소를 가져온다.
- Stream은 요청할 때만 요소를 계산하여 내부 반복을 사용하여 추출 요소만 선언하면 알아서 반복 처리한다.
    - 스트림 요소를 따로 추가나 제거하는 작업이 불가

## 외부 반복 VS 내부 반복

### 외부 반복

- Collection은 외부 반복을 사용하는데 명시적으로 컬렉션 항목을 하나씩 가져와 처리해야 하기 때문에 최적화에 불리하다.

### 내부 반복

- Stream에서 내부 반복을 사용하는데 병렬 처리를 하면서 최적화된 순서로 처리하기 때문에 최적화에 유리하다.

## Stream 연산

### 중간 연산과 최종 연산

- 두 연산으로 나누는 이유는 중간 연산들은 스트림을 반환하여 모두 한꺼번에 병합하여 연산을 처리하여 최종 연산에서 처리한다.

### 중간 연산

- filter - true인 요소 반환
- distinct - 중복 제거
- limit - 주어진 사이즈 이하의 크기를 갖도록 반환
- skip - 처음 n개의 요소를 생략하고 스트림 반환
- map - 매핑 함수를 통해 나온 결과물을 스트림으로 반환
- flatmap - 스트림 콘텐츠로 매핑

### 최종 연산

- allMatch - 모든 요소가 조건에 일치하는지 검사
- anyMatch - 하나의 요소라도 조건에 만족하는지 검사
- noneMatch - 모든 요소가 조건에 일치하지 않는지 검사
- findAny - 임의의 요소 반환
- findFirst - 첫번째 요소 반환
- reduce - 첫번째 인자로 초기값을 받고 두 번째 인자로 계산할 함수, 세 번째로 병렬 스트림에서 각 스레드 계산 결과 합치는 함수를 넣고 연산을 계산 반복하여 결과를 반환
- collect - list나 map 등의 컬렉션을 만들어 반환
- forEach - 각 요소에 람다식 적용
- count - 스트림 요소 개수 반환

## Reference

[https://gyoogle.dev/blog/computer-language/Java/Stream.html](https://gyoogle.dev/blog/computer-language/Java/Stream.html)