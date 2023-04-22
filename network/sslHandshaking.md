# SSL Handshaking

## 개념

### ssl handshaking

- HTTPS 통신에서 클라이언트와 서버가 데이터를 통신을 할 때 사전에 ssl 인증서를 통한 신뢰성을 기반으로 연결하고 공개키를 통해 암호화 통신을 하기 위한 과정

## 진행 과정

### Client Hello

- 클라이언트가 서버에게 client hello 메시지를 보내 버전, 암호화 알고리즘, 압축 방식을 전달

### Server Hello

- 서버는 클라이언트에게 server hello 메세지를 보내 세션 ID와 CA 공개 인증서를 전달
- CA 인증서에는 서버와 클라이언트가 이후에 통신할 때 사용할 대칭키를 암호화할 때 사용할 서버 측의 공개키를 CA의 비밀키로 암호화한다.

### Verify server certificate

- 클라이언트는 서버의 인증서가 유효한지 CA 목록을 통해 확인
- 브라우저에 저장된 CA의 공개키를 통해 ssl 인증서를 복호화하고 서버 측의 공개키를 가져온다.

### Client key exchange

- 클라이언트는 의사 난수 바이트를 생성해 서버의 공개키로 암호화하고 서버에 전달
- 의사 난수 바이트는 이후 대칭키를 정하는데 사용된다.
- 서버 측에서는 서버의 개인키로 복호화하여 의사 난수 바이트를 가져온다.

### Send client certificate

- 서버가 클라이언트 인증서를 요청한 경우에는 클라이언트 개인키로 암호화된 임의의 바이트 문자열을 전달

### Verify client certificate

- 서버는 클라이언트의 인증서를 확인

### Client finished

- 클라이언트는 교환 내역을 해시한 값을 대칭키로 암호화하여 전달

### Server finished

- 서버도 스스로 해시 값을 생성해 도착한 값과 비교하여 같으면 대칭키로 암호화하여 전달

### Exchange message

- 이후 서버와 클라이언트는 대칭키로 암호화된 데이터를 통신할 수 있다.

## Reference

[https://wangin9.tistory.com/entry/브라우저에-URL-입력-후-일어나는-일들-5TLSSSL-Handshake](https://wangin9.tistory.com/entry/%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80%EC%97%90-URL-%EC%9E%85%EB%A0%A5-%ED%9B%84-%EC%9D%BC%EC%96%B4%EB%82%98%EB%8A%94-%EC%9D%BC%EB%93%A4-5TLSSSL-Handshake)