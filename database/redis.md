# Redis & Memcached

## Redis

### 개념

- key-value 형태의 비정형 데이터를 저장하고 관리하는 오픈 소스 데이터베이스 관리 시스템
- 데이터베이스, 캐시, 메세지, 브로커로 사용되는 인메모리 DB

### 사용 목적

- 데이터베이스는 물리 디스크에 데이터를 저장하는 방식이라 속도가 느리다.
- 이러한 이유로 캐시 서버를 사용
    - 데이터베이스를 여러 번 거치는 것이 아니라 캐시 서버에서 저장된 값을 사용해서 속도 향상

### 특징

- key - value 형식의 구조로 쿼리를 사용하지 않아 속도가 빠르다.
- 물리 디스크에 저장하는 것이 아니라 메모리에 저장하여 속도가 빠르다.
- String, Sets, Sorted Sets, Hashes, Lists의 자료구조를 지원
- Single threaded로 구동한다.
    - 하나의 명령어가 처리되고 난 뒤 다른 명령어 처리

### 주의점

- 서버에 장애가 발생하였을 때 운영 플랜 필요
    - 인메모리 db를 사용하여 데이터 유실 가능성 존재
- 싱글 스레드로 하나의 긴 명령은 피해야 한다.

### Backup

- 인메모리에 데이터를 저장하기 때문에 backup 기능이 필요
- AOF(Append Only File)
    - 명령을 실행할 때마다 파일에 저장하여 데이터 손실이 없다.
- RDB(snapshot)
    - 특정 시점에 메모리에 있는 데이터를 바이너리 파일로 저장

## Memcached

### 개념

- redis와 마찬가지로 인메모리 key-value 오픈소스 데이터베이스

### 특징

- String 자료구조만 지원
- multi thread로 구동
- 데이터를 메모리에만 저장한다.
- 상대적으로 적고 정적인 데이터를 캐싱하는 경우에 사용

## Reference

[https://wildeveloperetrain.tistory.com/21](https://wildeveloperetrain.tistory.com/21)