# SQL Injection

## 개념

### SQL Injection

- 보안상 취약점을 이용하여 SQL문을 주입하여 실행하게 하여 DB가 비정상적으로 동작하도록 하는 공격

## 공격 기법

### Error Based SQL Injection

- 논리적 에러를 이용한 공격
- 예제
    - where id = 뒤쪽에 or 1=1—를 넣어 로그인할 때 user table 모두 조회 가능

### Union based SQL Injection

- 두 개의 쿼리문에 대한 결과를 통합해 하나의 테이블로 보여주게 하는 키워드
- 정상적인 쿼리문에 하나의 추가 쿼리를 삽입하여 원하는 정보 획득
- 테이블 칼럼 수와 데이터 형이 같아야 한다.
- 예제
    - 게시글 조회에서 칼럼 수에 맞춰 union select null, id, password from users — 삽입
    - 사용자의 id, password가 화면에 출력된다.

### Blind SQL Injection

- boolean based
    - 쿼리를 통해 나온 값이 참인지 거짓인지 확보하여 정보를 취득
    - 예제
        - limit 키워드를 통해 하나의 테이블을 가져와 substr으로 첫 글자를 ascii로 변환하여 특정 숫자 값을 비교하여 참인지 비교한다.
        - 테이블의 이름을 알아낼 수 있다.
- time based SQL
    - 쿼리 결과를 특정 시간만큼 지연
    - length를 통해 db 이름을 가져와 특정 숫자를 넣어 참이면 sleep이 작동하도록 구현
    - 특정 숫자를 변형하여 db 이름 길이 확보 가능

### Stored Procedure SQL injection

- stored procedure - 일련의 쿼리들을 모아 함수처럼 만들어 둔 것
- MS SQL에서 사용할 수 있는 xp_cmdshell을 통해 윈도우 명령어를 실행 가능
- 시스템 권한을 획득해야 해서 난이도가 높다.

### Mass SQL injection

- 다량의 SQL injection 공격
- DB 값을 변조하여 DB에 악성 스크립트를 삽입하고 변조된 사이트에 접속 시 좀비 pc로 감염되게 하는 공격
- 감염된 좀비 pc는 DDos 공격에 활용
    - 대량의 패킷이나 요청으로 시스템 마비시키는 공격

## Reference

[https://choco4study.tistory.com/10](https://choco4study.tistory.com/10)