---
description: 세션과 쿠키에 대해 각각에 대해 알아보고 차이점을 알아보자.
---

# 세션과 쿠키의 차이는?

### 세션이란?

* 일정 시간 동안 같은 사용자로부터 들어오는 요구를 하나의 상태로 보고, 그 상태를 유지시키는 기술이다.
  * 일정 시간은 사용자가 웹 브라우저를 통해 웹 서버에 접속한 시점부터 웹 브라우저를 종료하여 연결을 끝내는 시점을 말한다.
  * 즉, 방문자가 웹 서버에 접속해 있는 상태를 하나의 단위로 보고 그것을 세션이라고 한다.
  * 웹 서버에 사용자 정보(session Id)를 저장한다.
  * 저장 데이터에 제한이 없다.(서버 용량에 비례)

### 쿠키란?

* HTTP의 일종으로 사용자가 어떤 웹 사이트에 방문할 경우, 사이트가 사용하고 있는 서버에서 사용자의 컴퓨터에 저장하는 작은 기록 정보 파일이다.
  * 이름, 값, 만료일, 경로 정보로 구성되어 있다.
  * 클라이언트에 총 300개의 쿠키를 저장할 수 있다.
  * 하나의 도메인 당 20개의 쿠키를 가질 수 있다.
  * 하나의 쿠키에는 4KB까지 저장 가능하다.

### 차이점은?

* 사용자의 정보가 저장되는 위치가 다르다. 쿠키는 서버의 자원을 전혀 사용하지 않으며, 세션은 서버에 저장된다.
* 보안 면에서 서버에 보관되는 세션이 더 우수하다. 쿠키는 로컬에 저장되기 때문에 변질이나 스니핑 등 보안에 취약하다.
* **라이프 사이클** : 쿠키는 파일로 저장되기 때문에 브라우저를 종료해도 정보가 유지될 수 있다.(만료기간을 따로 지정해 쿠키를 삭제할 때까지 유지할 수도 있다.) 세션은 브라우저가 종료되면 만료기간에 상관없이 삭제된다.(만료기간 정할 순 있음)
* 쿠키는 쿠키에 정보가 있기 때문에 서버에 요청 시 속도가 빠르고, 세션은 정보가 서버에 있기 때문에 처리가 필요해 비교적 느린 속도를 낸다. 따라서 속도 면에서는 쿠키가 더 우수하다.
