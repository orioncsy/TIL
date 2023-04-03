# Join

## 개념

### Join

- 두 개 이상의 테이블을 연결하여 데이터를 검색할 때 사용하는 sql 문의 하나이다.

## 종류

### Inner Join

- ON 절의 조건을 만족하는 데이터만 가져와서 출력

### Natural Join

- 두 테이블에서 동일한 칼럼명을 가지는 칼럼이 모두 내부 조인된다.
- 타입과 이름이 동일한 칼럼명이 존재해야 한다.

### Full Outer Join

- 공통된 부분뿐만 아니라 두 테이블의 모든 데이터를 가져온다.
- mySQL에서는 지원하지 않기 때문에 Left Outer Join과 Right Outer Join을 union해야 한다.

### Left Outer Join

- 왼쪽 테이블을 기준으로 일치하는 행만 결합하고 일치하지 않는 부분은 null로 채운다.

### Right Outer Join

- 오른쪽 테이블을 기준으로 일치하는 행만 결합하고 일치하지 않는 부분은 null로 채운다.

### Cross Join

- 두 테이블의 데이터의 모든 조합
- 테이블의 개수를 곱한 갯수만큼의 데이터가 조회

## Reference

[https://doh-an.tistory.com/30](https://doh-an.tistory.com/30)