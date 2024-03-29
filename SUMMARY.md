# Table of contents

* [백엔드 기술면접 대비](README.md)
* [면접 질문 관련 사이트 모음](undefined.md)
* [기술적인 부분을 포함해서 1분 자기소개를 해주세요.](1-..md)
* [Basic](basic/README.md)
  * [사용자 인증 방법은 어떤 것들이 있는가?(작성중)](basic/undefined/README.md)
    * [SSO(Sing Sign On)은 무엇인가?(작성중)](basic/undefined/sso-sing-sign-on.md)
    * [JWT에 대해 설명해주세요, 사용하면 장점과 단점?](basic/undefined/jwt/README.md)
      * [JWT 토큰이 아닌 인증 기능 구현을 하기 위한 다른 방법은 뭐가 있을까요?](basic/undefined/jwt/jwt.md)
    * [세션과 쿠키의 차이는?](basic/undefined/undefined/README.md)
      * [세션을 이용한 인증 기능을 사용할 때 서버를 다중화 한다면 문제점과 해결방안은?(Sticky Session)](basic/undefined/undefined/sticky-session.md)
    * [대칭키와 비대칭키 암호화 방식의 차이는?](basic/undefined/undefined-1.md)
  * [무중단 배포 방법을 알고있는가?](basic/undefined-1/README.md)
    * [A/B 테스트란 무엇인가?](basic/undefined-1/a-b.md)
  * [REST API](basic/rest-api.md)
  * [OOP](basic/oop/README.md)
    * [객체지향이란?](basic/oop/undefined.md)
    * [객체지향 5대 원칙 - SOLID](basic/oop/5-solid.md)
  * [형상관리란 무엇인가?](basic/undefined-2.md)

## OS

* [Process 란?](os/process/README.md)
  * [Thread와 Multi Thread란?](os/process/thread-multi-thread.md)

## Network

* [HTTP](network/http/README.md)
  * [HTTP 메서드와 각 메서드의 역할은?](network/http/http.md)
  * [멱등성과 멱등성을 지원하는 HTTP 메서드는?](network/http/http-1.md)
  * [HTTPS란?](network/http/https/README.md)
    * [SSL 인증서란 무엇인가?](network/http/https/ssl.md)
  * [Stateful과 Stateless란?](network/http/stateful-stateless.md)
* [OSI 7계층이란 무엇인가?](network/osi-7.md)

## Language

* [Java](language/java/README.md)
  * [for문과 stream의 차이점은?](language/java/for-stream.md)
  * [일급 컬렉션이란?(작성중)](<language/java/undefined (2).md>)
  * [Reflection 이란?](language/java/reflection.md)
  * [해시 충돌(hashMap,hashSet...)(작성중)](language/java/hashmap-hashset....md)
  * [동일성(Identity)과 동등성(Equality) 비교](language/java/identity-equality.md)
  * [Java의 Collection이란?](language/java/undefined.md)
  * [Priority Queue란?(작성중)](language/java/priority-queue.md)
  * [Enum 사용해보셨나요? Enum이란 무엇인가요?](language/java/enum-enum.md)
  * [Overriding과 Overloading](language/java/overriding-overloading.md)
  * [추상클래스와 인터페이스는 무엇이고, 차이점은 무엇인가?](language/java/undefined-1.md)
  * [ArrayList와 LinkedList의 차이점](language/java/arraylist-linkedlist.md)
  * [final 키워드를 사용하면?](language/java/final.md)
  * [제네릭이란?](language/java/undefined-2.md)
  * [Stream이란?](language/java/stream.md)
  * [stream method 중 map과 flatmap 차이점](language/java/stream-method-map-flatmap.md)
  * [람다식(Lambda Expression)이란?](<language/java/undefined (1).md>)
  * [Java의 특징이란?](language/java/java/README.md)
    * [가비지 컬렉션이란?](language/java/java/undefined.md)
  * [클래스와 객체란?](language/java/undefined-3.md)
  * [DTO, VO, ENTITY 차이점](language/java/dto-vo-entity.md)
* [Kotlin](language/kotlin.md)

## Framework

* [Spring](framework/spring/README.md)
  * [@Transactional에 대해서 설명해주세요.](framework/spring/transactional-..md)
  * [스프링 의존성 주입 방법 3가지는?](framework/spring/3.md)
  * [스프링 트라이앵글 - IoC, AOP, PSA](framework/spring/ioc-aop-psa.md)
  * [스프링 DI](framework/spring/di/README.md)
    * [같은 인터페이스의 구현체 클래스 두 개 이상이 빈으로 등록되면 어떻게 의존성을 주입 할 수 있는가?](framework/spring/di/undefined.md)
  * [Filter와 Interceptor](framework/spring/filter-interceptor.md)
* [Spring Data JPA](framework/spring-data-jpa/README.md)
  * [N+1 문제가 무엇이고, 해결 방법은 어떤 것인가?(작성중)](framework/spring-data-jpa/n+1.md)

## Database

* [옵티마이저란 무엇인가?](database/undefined.md)
* [데이터베이스의 부하 분산을 위한 방법으로 사용되는 클러스터링, 리플리케이션, 샤딩이란 무엇인가?](database/undefined-1.md)
* [트랜잭션 격리수준(Isolation Level)이란?(링크)](database/isolation-level.md)
* [낙관적 락(Optimistic Lock) 과 비관적 락(Pessimistic Lock)이란?](database/optimistic-lock-pessimistic-lock.md)
* [RDB와 NoSQL 데이터베이스의 차이점은?](database/rdb-nosql/README.md)
  * [Redis란?](database/rdb-nosql/redis.md)
  * [Redis란 무엇인가?](database/rdb-nosql/redis-1.md)
* [인덱스(Index)란?](database/index.md)
* [MySQL에서 Join과 UNION의 차이점은?](database/mysql-join-union.md)
* [클러스터드 인덱스 (Clustered Index), 넌 클러스터드 인덱스 (Non Clustered Index)(작성중)](database/clustered-index-non-clustered-index.md)

## Design Pattern

* [싱글톤 패턴](design-pattern/undefined.md)
