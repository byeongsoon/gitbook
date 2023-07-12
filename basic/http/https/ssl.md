---
description: >-
  HTTPS는 공인된 기관에서 인증서를 발급받아 요청마다 인증받은 서비스임을 확인한다. 이때 인증서에 사용되는 SSL 인증서란 무엇인지
  알아보자.
---

# SSL 인증서란 무엇인가?

### SSL 인증서란?

* SSL 인증서
  * SSL방식에 사용하는 전자화된 문서로, 공인된 인증기관(Certificate Authority)에서 발급한다.
* CA(Certificate Authority)
  * SSL인증서를 발급하는 공인된 민간기업들
  * CA로 유명한 회사로는 Comodo, GoDaddy, Let's Encrypt(무료) 등이 있다.
  * 각 브라우저(크롬, 사파리 등)들은 공인 CA들의 목록을 내부에 저장하고 있다.

### 암호화 방식

* 대칭키 방식: 1개의 key 사용
  * 방식: 암호화하고 복호화 하는데 동일한 비밀번호(key)를 사용
  * 단점: 서버와 브라우저가 동일한 key를 사용하므로, 외부에 노출되면 보안에 취약해진다.
* 공개키(비대칭키) 방식: 2개의 key 사용
  * 2개의 key를 만들어서 하나는 나(서버)만 갖고(비밀키:Private Key), 하나는 모두(브라우저)에게 나눠준다(공개키: Public Key)
  * 방식: '공개키'로 암호화한 건 '비밀키'로 복호화할 수 있고, '비밀키'로 암호화한 건 '공개키'로 복호화할 수 있다.
  * 데이터 통신 활용
    * 예) 로그인: 브라우저에서 ID/PW를 공개키로 암호화해서 보내면, 서버는 비밀키로 복호화해서 로그인 처리한다.
  * 인증 활용
    * 예) 전자서명: 서버가 비밀키로 암호화하여 보낸 데이터를, 브라우저가 공개키로 복호화할 수 있다면 서버가 비밀키의 주인임을 확인 수 있다.

### HTTPS/SSL 기본원리

1. 내 서버에서 '비밀키/공개키'를 생성한다.
2. 공인기관(CA)에서 내 서버의 SSL인증서를 발급 받는다.
   * SSL인증서는 'CA의 비밀키'로 암호화 되어 있으며,
   * 인증서 내부에는 '내 서버의 공개키'가 저장되어 있다.
3. 내 서버에 인증서를 저장하고, SSL 통신을 설정해둔다.
4. 브라우저가 내 서버에 접속하면 인증서를 보내준다.
5. 브라우저는 받은 인증서를 'CA의 공개키'로 복호화한다.
   * 인증서는 '발급한 CA의 비밀키'로 암호화 되어 있으며,
   * 브라우저(크롬, 사파리 등)은 '공인된 CA들의 공개키'를 내부에 보관하고 있다.
6. 인증서 복호화에 성공한다면, 해당 인증서가 CA가 발급한 것임이 증명된다.
   * 인증서를 보낸 '내 서버'도 CA가 인증한 서버임이 증명된다.
7. 복호화한 인증서에서 '내 서버의 공개키'를 취득하여 데이터 통신에 활용한다.
   * 서버와 주고 받는 데이터 자체는 '대칭키 방식'으로 암호화 하고,
   * '대칭키 방식에 사용된 key'를 '내 서버의 공개키'로 암호화 한다.

### &#x20;참고

{% embed url="https://curryyou.tistory.com/207" %}