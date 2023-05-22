# Linux command

## Linux 명령어 모음

### 명령어 세부 사항

- man 명령어를 통해 세부 사항 확인 가능

### 시스템 종료 및 재부팅

- shutdown, halt, init 0, poweroff
    - 시스템 종료
- reboot, init 6, shutdown -r now

### 디렉터리

- pwd
    - present working directory(현재 위치하는 디렉터리)
- cd
    - change directory(디렉터리 위치 변경)
- ls
    - 현재 디렉터리 내 파일 및 디렉터리 표시
- mkdir
    - make directory(디렉터리 생성)
- rmdir
    - remove directory(디렉터리 제거)
    - r 옵션으로 안에 있는 파일 제거

### 파일

- touch
    - 파일 크기 0인 파일 생성
- cp
    - 파일 복사
    - 디렉터리 내부까지 복사하기 위해 cp -r 사용
- mv
    - 파일 이동
- rm
    - 파일 삭제
    - 폴더 삭제의 경우 rm -r로 사용
- cat
    - 화면에 파일 내용 출력
- more
    - more [파일 이름] 혹은 | more을 통해 긴 출력을 끊어 읽을 때 사용
    - 위에서부터 파일 내요을 읽을 수 있고 엔터를 통해 한 줄씩 읽고 엔터를 통해 페이지로 읽을 수 있다.
    - 화면을 나오고 싶을 경우 q로 나온다.
    - 파일을 다 읽으면 자동으로 종료
- less
    - more과 유사하나 한 번에 읽지 않아 속도가 빠르고 기능이 더 많다.
    - more은 위에서 아래로 이동이 가능하지만 less는 위아래로 이동 가능
    - 파일을 다 읽으면 자동으로 종료되지 않는다.
    - 위아래 화살표나 page up, page down 사용 가능
- head
    - head -n [숫자]
    - 숫자 라인만큼 위에서 출력
- tail
    - tail -n [숫자]
    - 숫자 라인만큼 아래에서 출력
- find
    - 특정 파일 찾기
    - 하위 디렉터리에 존재하는 파일 찾기
    - name으로 대소문자 구분하여 검색
    - iname으로 대소문자 구분하지 않고 검색
- grep
    - 특정 패턴을 이용해 파일 찾기
    - 하위 디렉터리를 포함해 모든 파일에서 원하는 단어 찾기
    - i로 대소문자 구분 없이 검색
    - n 파일의 몇 번째 라인에 있는지 표시
    - r 하위 디렉터리까지 검색
- 리다이렉션파일에 해당 내용을 넣을 때 사용는 덮어쓰기 할 때 사용
- echo
    - 다음 내용 출력
- awk
    - 패턴과 액션을 정의하여 데이터 가공 출력
- file
    - 파일 종류 확인
- which
    - 특정 명령어의 실행 파일의 위치를 출력

### 네트워크

- ping
    - ICMP 패키지를 대상의 IP에 전송하여 통신에서 지연을 찾아 패킷 손실을 확인
    - 전송하는 데이터 바이트, 대상 IP 주소, 각 패킷의 sequence number, ttl(time to live), 패킷이 왕복하는 데 걸리는 시간
- ifconfig
    - window에서 ipconfig과 같은 기능
- netstat
    - 네트워크 연결 상태 확인
- traceroute
    - 패킷 손실이 발생하였을 경우 손실된 위치를 확인하기 위해 사용
    - windows에서 tracert와 같은 기능
- route
    - 리눅스에서 라우팅 테이블 구성 상태 출력

### 시간

- clock
    - CMOS의 시간 조절 명령어
    - CMOS 셋업은 하드웨어 기기들의 정보들을 저장하는 것이며 BIOS는 등록된 하드웨어 기기들을 연결하는 역할
- date
    - 시간, 날짜 정보 출력
- rdate
    - 서버로부터 날짜, 시간을 받아 시스템에 설정

### 패키지

- npm
    - npm 패키지 설치 및 삭제, 관리하는 명령어
- yum
    - 인터넷으로 npm 패키지가 저장된 서버에 접속해 필요한 패키지 설치

### 프로세스

- free
    - 시스템 메모리 정보 출력
- ps
    - 프로세스 목록 출력
    - e는 모든 프로세스 출력하고 -f는 모든 정보 출력
- pstree
    - 프로세스 목록을 트리 형태로 출력
- top
    - 리눅스 시스템 상황을 전반적으로 모니터링
- kill
    - 특정 프로세스에게 signal을 보내는 명령
- killall
    - 특정 프로세스 모두 종료
- killall5
    - 모든 프로세스 종료

### 압축

- tar, bzip2, gzip
    - 압축 및 해제 명령

### 권한

- chmod
    - 특정 파일이나 폴더의 권한 변경
- chown
    - 파일이나 디렉터리 소유자와 소유 그룹 변경
- chgrp
    - 파일이나 디렉터리의 소유 그룹만 변경
- umask
    - 특정 파일이나 디렉터리를 생성할 때 권한을 자동으로 설정

### 작업

- at
    - 지정된 시간 내에 명령어나 프로그램 실행
- crontab
    - 반복적인 작업을 수행하는 명령

### 계정 및 그룹

- useradd
    - 계정 생성
- password
    - 사용자 계정 비밀번호 설정
- userdel
    - 계정 삭제
- usermod
    - 계정 정보 수정
- groupadd
    - 그룹 생성
- groupdel
    - 그룹 삭제
- groups
    - 그룹 확인
- newgrp
    - 자신이 속한 그룹 변경

### 실행 방식

- jobs
    - 실행한 프로세스를 번호와 함께 확인 가능
- fg
    - fg %[번호]를 통해 해당 번호의 프로세스를 foreground로 실행
- bg
    - bg %[번호]를 통해 해당 번호의 프로세스를 background로 실행
    - 명령어 끝에 &를 붙여 백그라운드로 실행 가능

### 메시지

- mesg
    - 메시지 응답 가능 여부 설정
- talk
    - 사용자들과의 대화
- wall
    - 모든 사용자에게 메시지 보내기
- write
    - 사용자에게 메시지 전송

## Reference

[https://vaert.tistory.com/103](https://vaert.tistory.com/103)