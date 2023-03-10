# 접근 제어자

## 개념

### 접근 제어자

- 변수, 메서드, 생성자에 대해 접근 권한을 지정 가능
- public, protected, private, default(아무것도 붙이지 않는 경우)로 구분

## 종류

### public

- 모든 영역에서 접근 가능

### protected

- 해당 패키지와 상속받은 클래스에서 접근 가능

### default

- 해당 패키지에서만 접근 가능

### private

- 클래스 내부에서만 접근 가능

## 목적

- 자바의 특성인 캡슐화를 실현
- 외부에서의 접근을 제한하여 정보를 은닉하는 효과
- 외부에서 변수 값을 잘못 변경할 수 있기 때문에 setter나 getter를 통해 값을 수정 및 조회하여 안전한 코드 작성

## Reference

[https://peemangit.tistory.com/394](https://peemangit.tistory.com/394)