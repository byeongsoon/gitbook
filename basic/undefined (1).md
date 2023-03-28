---
description: 22년 이스트소프트 면접에서 들었던 질문으로 무중단 배포를 위한 방법이 무엇이 있는지 알아보고 각각이 어떻게 다른지 살펴보자.
---

# 무중단 배포 방법을 알고있는가?

### 무중단 배포란?

단어의 뜻 그대로 서비스하는 애플리케이션의 중단 없이 배포가 가능한 것을 말한다. 보통 로컬환경에서 개발을 진행할 때 추가로 작성한 소스코드를 적용하기 위해 서버를 재시작한다. 이때 서비스는 중단되고 배포가 완료되면 다시 서비스가 가능하다.

무중단 배포에는 크게 3가지의 방법이 있다.

### 롤링 배포(Rolling Update)

* 인스턴스를 늘리지 않고, 하나씩 새로운 버전으로 업데이트 하면서 배포한다. 일반적인 배포를 의미한다.
* 배포가 진행될 때 사용중인 인스턴스로 트래픽이 몰리는 문제가 있다.
* 버전간 호환성이 맞지않는 순간이 있다.

### 블루 그린 배포(Blue/Green Deployment)

* 구버전과 같은 환경으로 신버전을 미리 준비하여 로드밸런서의 라우팅을 한번에 전환시킨다.
* 구버전의 환경을 재활용하거나 롤백하기 쉽다.
* 구버전과 신버전이 동일한 환경이기 때문에 시스템 자원이 두배로 든다.

### 카나리 배포(Canary Release)

* 소수만 사용하는 환경에 신버전을 배포하고 문제를 관찰한다. 문제가 없다면 신버전으로의 트래픽을 단계적으로 늘린다.
* 블루 그린 배포와 유사하지만 한번에 전환이 아닌 **단계적 전환**이다.
* 문제를 빠르게 발견할 수 있다.
* A/B 테스트로 활용 및 성능 모니터링에 유용하다.