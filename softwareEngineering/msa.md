# MSA

## 개념

### Micro Service Architecture

- 애플리케이션 단위를 기능별로 컴포넌트를 나누어 조합하여 개발하는 방식

### 배경

- 기존 Monolithic 방식은 모든 기능을 하나의 애플리케이션에서 비즈니스 로직을 구현한다.
    - 실행 파일이 하나라서 배포가 쉽고 하나의 코드 베이스를 사용하여 개발이 용이하며 하나의 API로 MSA의 여러 API가 작업하는 효과를 낼 수 있으며 테스트를 간소화할 수 있고 디버깅이 쉽다.
- 작은 사이즈의 프로젝트에서는 기존 방식이 유리하지만 큰 프로젝트에서 문제점들이 존재

### 기존 방식의 문제점

- 빌드/테스트 시간 증가
    - 하나의 기능을 수정할 때도 전체 시스템을 빌드해야 해서 유지 보수가 어려워진다.
- 작은 문제가 시스템 전체에 영향을 줄 수 있다.
    - 하나의 서비스가 트래픽 문제로 서버가 다운되면 전체 시스템이 중단된다.
- 확장성 불리
    - 하나의 서비스를 확장하기 위해 전체 시스템을 확장해야 한다.

## Monolithic과의 차이점

### Monolithic vs MicroService

- 단위 설계
    - 기존 방식은 전체 애플리케이션이 단일 단위로 설계되고 개발
    - MSA는 각 서비스가 단일 비즈니스를 수행하고 유연하게 결합된 서비스로 구성
- 기능 재사용
    - 기존 방식은 애플리케이션 재사용이 제한
    - MSA는 모든 클라이언트에게 해당 기능을 표시하는 API 정의
- 애플리케이션 내 통신
    - 기존 방식은 내부 프로시저로 애플리케이션 구성 요소 간에 통신
    - MSA는 HTTP 프로토콜 기반 REST API를 호출하여 통신
- 기술 유연성
    - 기존 방식은 단일 프로그래밍 언어를 사용
    - MSA는 각각의 서비스가 각자의 프로그래밍 언어와 프레임워크를 사용 가능
- 데이터 관리
    - 기존 방식은 중앙집중식으로 전체 응용 프로그램에서 하나 이상의 데이터베이스 사용
    - MSA는 서비스마다 자체 데이터베이스 사용
- 배치
    - 기존 방식은 기존 전체 애플리케이션을 수정하여 재배포해야 한다.
    - MSA는 다른 서비스에 영향을 주지않고 독립적으로 배치
- 유지 관리 기능
    - 기존 방식은 애플리케이션 범위가 넓어 코드가 복잡
    - MSA는 서비스마다 독립적이기 때문에 각 서비스는 단순하고 유지 관리가 용이
- 복원성
    - 기존 방식은 구성 요소의 오류가 전체 시스템에 영향을 준다.
    - MSA는 여러 서비스에 분산되어 있어 하나의 서비스가 실패해도 다른 서비스를 계속 사용 가능
- 확장성
    - 기존 방식은 애플리케이션의 특정 부분을 수정할 때 전체 애플리케이션 수정
    - MSA는 각각의 서비스를 독립적으로 확장 가능

## MSA 단점

- 서비스 간 통신을 할 때 API를 사용하여 통신하기 때문에 통신 속도가 느리다.
- 서비스 별로 통신에 맞는 데이터로 변환해야 한다.
- DB를 개별적으로 운영하기 때문에 트랜잭션을 묶는 작업이 어렵다.

## Reference

[https://gyoogle.dev/blog/computer-science/software-engineering/MSA.html](https://gyoogle.dev/blog/computer-science/software-engineering/MSA.html)