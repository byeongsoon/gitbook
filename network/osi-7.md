---
description: >-
  데이터 통신을 위해 네트워크 프로토콜이 통신하는 구조를 7개의 계층으로 분리하여 각 계층간 상호 작동하는 방식인 OSI 7계층에 대해
  알아보자.
---

# OSI 7계층이란 무엇인가?

### 작동 원리 <a href="#undefined" id="undefined"></a>

1. OSI 7계층은 응용, 표현, 세션, 전송, 네트워크, 데이터링크, 물리계층으로 나뉨.
2. 전송 시 7계층에서 1계층으로 각각의 층마다 인식할 수 있어야 하는 헤더를 붙임(캡슐화)
3. 수신 시 1계층에서 7계층으로 헤더를 떼어냄(디캡슐화)
4. 출발지에서 데이터가 전송될 때 헤더가 추가되는데 2계층에서만 오류제어를 위해 꼬리부분에 추가됌
5.  물리계층에서 1, 0 의 신호가 되어 전송매체 (동축케이블, 광섬유 등)을 통해 전송\


    <figure><img src="https://velog.velcdn.com/images%2Fcgotjh%2Fpost%2F52907c8c-c149-4943-ad21-3996f44f912f%2F995EFF355B74179035.jpg" alt=""><figcaption></figcaption></figure>

### 물리계층(Physical Layer) <a href="#physical-layer" id="physical-layer"></a>

* 7계층 중 최하위 계층.
* 주로 전기적, 기계적, 기능적인 특성을 이용해 데이터를 전송.
* 데이터는 0과 1의 비트열, 즉 On, Off의 전기적 신호 상태로 이루어져 해당 계층은 단지 데이터를 전달.
* 단지 데이터 전달의 역할을 할 뿐이라 알고리즘, 오류제어 기능이 없음
* 장비로는 케이블, 리피터, 허브가 있음

### 데이터링크 계층(Data-Link Layer) <a href="#data-link-layer" id="data-link-layer"></a>

* 물리적인 연결을 통하여 인접한 두 장치 간의 신뢰성 있는 정보 전송을 담당(Point-To-Point 전송)
* 안전한 정보의 전달이라는 것은 오류나 재전송하는 기능이 존재
* MAC 주소를 통해서 통신
* 데이터 링크 계층에서 데이터 단위는 프레임(Frame)
* 장비로는 브리지, 스위치가 있음

### 네트워크 계층(Network Layer) <a href="#network-layer" id="network-layer"></a>

* 중계 노드를 통하여 전송하는 경우 어떻게 중계할 것인가를 규정
* 라우팅 기능을 맡고 있는 계층으로 목적지까지 가장 안전하고 빠르게 데이터를 보내는 기능을 가지고 있음(최적의 경로를 설정가능)
* 컴퓨터에게 데이터를 전송할지 주소를 갖고 있어서 통신가능(=우리가 자주 듣는 IP 주소가 바로 네트워크 계층 헤더에 속함)
* 네트워크 계층에서 데이터 단위는 패킷(Packet)
* 장비로는 라우터, L3 스위치가 있음

### 전송 계층(Transport Layer) <a href="#transport-layer" id="transport-layer"></a>

* 종단 간 신뢰성 있고 정확한 데이터 전송을 담당
* 송신자와 수신자 간의 신뢰성있고 효율적인 데이터를 전송하기 위하여 오류검출 및 복구, 흐름제어와 중복검사 등을 수행
* 데이터 전송을 위해서 Port 번호를 사용함.(대표적인 프로토콜로 TCP와 UDP가 있음)
* 전송 계층에서 데이터 단위는 세그먼트(Segment)

### 세션 계층(Session Layer) <a href="#session-layer" id="session-layer"></a>

* 통신 장치 간 상호작용 및 동기화를 제공
* 연결 세션에서 데이터 교환과 에러 발생 시의 복구를 관리

### 표현 계층(Presentation Layer) <a href="#presentation-layer" id="presentation-layer"></a>

* 데이터를 어떻게 표현할지 정하는 역할을 하는 계층
* 표현 계층은 세가지의 기능을 갖고 있습니다.
  1. 송신자에서 온 데이터를 해석하기 위한 응용계층 데이터 부호화, 변화
  2. 수신자에서 데이터의 압축을 풀수 있는 방식으로 된 데이터 압축
  3. 데이터의 암호화와 복호화\
     (MIME 인코딩이나 암호화 등의 동작이 표현계층에서 이루어짐. EBCDIC로 인코딩된 파일을 ASCII 로 인코딩된 파일로 바꿔주는 것이 한가지 예임)

### 응용 계층(Application Layer) <a href="#application-layer" id="application-layer"></a>

* 사용자와 가장 밀접한 계층으로 인터페이스 역할
* 응용 프로세스 간의 정보 교환을 담당
* ex) 전자메일, 인터넷, 동영상 플레이어 등



### 참고

{% embed url="https://velog.io/@cgotjh/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-OSI-7-%EA%B3%84%EC%B8%B5-OSI-7-LAYER-%EA%B8%B0%EB%B3%B8-%EA%B0%9C%EB%85%90-%EA%B0%81-%EA%B3%84%EC%B8%B5-%EC%84%A4%EB%AA%85" %}
