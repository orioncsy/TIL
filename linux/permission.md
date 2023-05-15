# Permission

## 개념

### Permission

- 시스템에 대한 읽기, 쓰기, 실행의 접근 권한 여부를 결정
- 리눅스에서 다중 사용자에 대한 가장 기초적인 보안 정책

## 접근 통제 기법

### DAC(Discretionary Access Control)

- 객체에 대한 접근을 사용자 개인이나 그룹의 식별자 기반으로 통제

### MAC(Mandatory Access Control)

- 관리자가 모든 접근 제어를 설정하여 통제

### RBAC(Role Based Access Control)

- 관리자가 사용자에게 역할을 부여하고 각 역할에 권한 설정

## 권한 종류

### 구분

- User, Group, Other 순으로 표현
- 각 영역에 대해 r(read), w(write), x(excute) 순으로 r은 4, w는 2, x는 1

### 표현

- 파일 모드
    - rwx, r-x 등으로 표현
- 8진수 모드
    - 7(rwx), 5(r-x) 등으로 표현

### 심볼릭 모드

- chmod를 통해 권한 변경 가능
    - chmod 권한 파일이름
- 대상은 u(user), g(group), o(other), a(all)로 표현
- 연산은 +(권한 추가), -(권한 제거), =(권한 설정)으로 표현
- 권한은 r, w, x로 표현
- u+r, o=x 등으로 표현

## Reference

[https://gyoogle.dev/blog/linux/Permission.html](https://gyoogle.dev/blog/linux/Permission.html)