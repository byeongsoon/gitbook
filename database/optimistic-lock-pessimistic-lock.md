---
description: 멀티 스레드 환경이나 트랜잭션 간의 동시성 제어를 위해 필요한 락에 대한 개념과 종류에 대해서 알아본다.
---

# 낙관적 락(Optimistic Lock) 과 비관적 락(Pessimistic Lock)이란?

### 락(Lock) 은 왜 필요한가? <a href="#lock" id="lock"></a>

짧은시간안에 요청이 많은 서버에서 여러 트랜잭션이 동시에 간읕 데이터에 업데이트를 발생시킬 경우에, 일부 요청이 유실디는 경우가 발생하여 장애로 이어질 수 있습니다.

DBMS 에서 특정 데이터에 대한 동시접근이 발생시 일관성과 무결성이 보장되어야 합니다. 이러한 락(Lock) 을 구현하는 방식은 크게 낙관적 락(Optimistic Lock) 과 비관적 락(Pessimistic Lock)으로 나뉩니다.\
(추후 설명하겠지만, 낙관적 락의 경우는 락을 구현한다는 표현은 사용하기 애매한 경계선에 있습니다.)

### 낙관적 락

낙관적 락(Optimistic Lock) 은 특정 자원에 대한 경쟁을 낙관적으로 바라보는 락 방식으로, **여러 트랜잭션이 데이터를 동시에 수정하지 않는다는 가정하에 트랜잭션 충돌을 방지하는 기법**입니다. 쉽게말해, 자원에 락을 걸어서 선점하지말고 커밋할 때 동시성 문제가 발생하면 그때 처리하자는 방법론입니다.

JPA 의 엔티티 특정 필드에 version 속성을 포함시켜서(@Version 어노테이션 붙이기), 별도의 락(Lock) 없이 트랜잭션 충돌을 방지할 수 있는 방법입니다.

```java
@Entity
public class Order {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private long orderId;
    private String orderName;
    
    @Version
    private long version;
    ...
}
```

방금 설명했듯이 데이터를 읽는 시점에서는는 락(Lock)을 별도로 설정 및 사용하지 않습니다. 하지만 트랜잭션에 의해 잘못된 업데이트(update) 을 알아서 방지하지 않습니다. 데이터를 읽는 시점에서는 락을 사용하지 않지만, 데이터를 수정하는 시점에서 앞에 읽은 데이터가 다른 사용자에 의해 변경되었는지 검사해야합니다.

* 장점 : 읽기 시점에서 락을 사용하지 않기 때문에 성능이 좋다. 동시 업데이트가 없는 경우 이 방법을 사용시 비관적 락보다 빠르게 조회 및 업데이트가 가능하다.
* 단점 : 여러 트랜잭션이 작업중에 하나의 트랜잭션이 공유자원을 변경할 경우, 다른 트랜잭션의 작업 내용이 거부된다.

### 비관적 락

비관적 락은 어떤 자원 경쟁을 비관적으로 바라보기 때문에, 여러 트랜잭션이 데이터를 동시에 수정할 것이라고 가정하는 기법입니다.\
하나의 트랜잭션이 데이터를 읽는 시점에서 락(Lock) 을 걸고, 조회 또는 업데이트 처리가 완료될 때까지 유지합니다.

쉽게 말해, **트랜잭션의 충돌이 발생한다고 가정하고 우선 락(Lock)을 걸고 보는방법입니다.**

#### 유의사항 : 데드락(DeadLock) 상황 발생 <a href="#deadlock" id="deadlock"></a>

* 쓰레드1 : 정보 A를 구하고 잠금
* 쓰레드2 : 정보 B를 구하고 잠금
* 쓰레드1 : 정보 B를 구하고자할때 블로킹(Blocking)
* 쓰레드2 : 정보 A를 구하고자할때 블로킹

이런 상황이라면 두 쓰레드 모두 영원히 작업을 끝낼 수 없는 교착상태, 즉 데드락(DeadLock) 에 빠지게됩니다. 데드락이 발생하지 않도록하려면 락을 시도할때 최대 잠금 시간을 지정해주면 됩니다.

* 장점 : 트랜잭션의 동시 접근을 확실하게 방지해서 순차적인 처리가 가능하다.
* 단점 : 한 트랜잭션 내용이 완료되기 전까지 다른 트랜잭션이 공유자원에 접근하지 못해서, 동시성이 떨어져 **대기가 길어지고 성능이 떨어질 수 있습니다.**\
  또한 각 트랜잭션이 서로 자원을 점유한 채, 서로의 자원을 요청하며 무한정 대기하는 **데드락(DeadLock)** 상황이 발생할 수 있습니다.



### 참고

{% embed url="https://velog.io/@msung99/JPA-%EB%82%99%EA%B4%80%EC%A0%81-%EB%9D%BDOptimistic-Lock-%EA%B3%BC-%EB%B9%84%EA%B4%80%EC%A0%81-%EB%9D%BDPessimistic-Lock-%EC%9D%84-%ED%86%B5%ED%95%9C-%EB%8F%99%EC%8B%9C%EC%84%B1-%EC%9D%B4%EC%8A%88-%ED%95%B4%EA%B2%B0" %}

{% embed url="https://velog.io/@lsb156/JPA-Optimistic-Lock-Pessimistic-Lock" %}

{% embed url="https://escapefromcoding.tistory.com/727" %}
