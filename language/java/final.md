---
description: final 키워드를 사용하면 필드와 메서드, 클래스에서 어떤 역할을 하는지 알아보자.
---

# final 키워드를 사용하면?

**final**은 클래스, 메서드, 멤버변수, 지역변수 선언시에 사용할 수 있다. 멤버변수나 지역변수에 final 키워드를 사용 시 값을 변경할 수 없는 상수로 만들 수 있다.(보통 상수로 만들 때 static 키워드와 함께 사용하여 정적으로 사용)

final은 '마지막의', '변경될 수 없음' 을 뜻하는 불변성을 의미한다.

#### 클래스에서의 final

클래스를 선언할 때 final 키워드를 사용하면 이 클래스는 변경될 수 없는, 확장될 수 없는 클래스가 된다.&#x20;

즉, 상속을 할 수 없는 클래스가 된다.(대표적인 final 클래스로는 String과 Math)

#### 메서드에서의 final

메서드를 선언할 때 final 키워드를 붙이게 되면 이 메서드는 오버라이딩을 할 수 없다.



> 면접 질문에서 final에 대한 질문이 나왔었는데 긴장한 탓에 메서드와 클래스에서의 역할이 기억나지 않았었다...
