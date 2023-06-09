# OOP (Object-Oriented Programming)
## 객체지향프로그래밍
<br/>

### 1) 객체
객체는 대상을 나타낸다. 예를 들어 사람 한 명 한 명도 모두 객체이다.  
객체지향에서의 객체는 프로그램 동작의 주체가 되는 요소를 말한다. 이 객체는 유/무형을 구분하지 않기 때문에 유형, 혹은 무형의 개념일 수도 있다.  
<br/>
모든 객체는 상태와 동작을 가진다. 예를 들어, TV를 구매한다면 사람들은 TV의 가격, 디자인, 성능 등을 적절히 고민해 구매할 것이다.  
이때 TV의 색, 인치, 가격 등은 TV가 가진 상태이다.  
TV 채널 조작, 다시 보기, OTT 서비스 이용 등은 TV의 기능이다.  
=> 모든 객체에는 상태와 동작이 존재한다.  
<br/>

### 2) 클래스
객체들이 공통적으로 갖는 속성들을 모아서 정의내린 것을 말한다.(추상화)  
예를 들어, 사람이라는 클래스는 눈, 코, 입 등의 속성이 존재하고 각 객체들은 다른 모양의 눈, 코, 입을 가지고 있으므로 다르게 분류된다.  
<br/>

### 3) 객체지향
객체지향은 객체를 통해 코드를 구성하는 방법론이다.  
모든 객체는 각 객체 특성에 부합하는 상태와 동작을 가지고, 객체 간 상호작용을 한다. 객체지향은 이러한 객체의 상호작용을 코드로 나타내는 것이다.  
<br/>

JAVA는 String, HashMap 등 모든 요소를 객체로 다룬다. JAVA가 필요한 객체를 메모리에 할당하고, 객체가 가진 변수나 메소드를 사용하여 코딩한다.  
<br/>

### 4) OOP의 특징
1) 추상화  
   목적과 관련 없는 부분을 제거하고 필요한 부분만을 표현한다.  
   객체들은 각기 다른 실제 모습을 가졌지만, 클래스는 객체가 가진 특징을 정의하는 추상화된 개념이다. 즉 추상화는 **객체들의 공통된 특징을 파악해 정의해 놓은 설계 기법**이다.  
   미술에서 추상화를 생각해 보자. 나무를 그린다고 했을 때 나무 잎사귀, 뻗어 있는 줄기, 트렁크, 뿌리, 열매 등 모든 모습을 표현하는 것이 아니라, 가장 대표적인 특징만을 추려 그리는 것이다.
2) 캡슐화  
   캡슐화는 알약 내용물을 감싸서 약을 쉽게 먹을 수 있도록 도와주는 것과 같다.  
   자바는 접근 제어자(public, protected, private..)를 가진다. private으로 정의된 속성은 외부에 노출시키지 않고 자신의 클래스에서만 사용한다.  
   즉 private으로 정의된 속성은 알약의 실제 내용물이다. 이 속성은 외부에 알려줄 필요가 없다.  
   <br/>
   캡슐화와 정보은닉은 동일한 개념이다. 캡슐화를 하면 불필요한 정보를 감출 수 있어 정보은닉이 가능하다.  
   예를 들어 TV의 리모컨을 사용할 때 리모컨의 내부 회로(private 속성)는 알 필요가 없다. 사용자는 리모컨의 조작 기능(public 속성)만 알면 된다.
3) 상속  
   강아지, 고양이는 포유류에 속한다. 포유류의 속성을 가지고 있지만, 많은 속성이 다르기 때문에 디테일하게 강아지, 고양이 종으로 나뉘게 되었다.  
   즉 포유류라는 클래스는 강아지, 고양이 클래스에 속성들을 물려준다. 이를 상속이라고 하고, 포유류와 강아지/고양이 클래스는 상속관계에 있다고 표현한다.  
   상속이 필요한 이유는 **코드의 중복을 없애기 위함**이다. 코드의 중복이 많아지면 개발 단계와 유지보수에 많은 비용이 든다.  
   상속 관계를 맺으면서 자식 객체를 생성할 때 부모 클래스의 속성들을 자동으로 물려 받기 때문에 자식 클래스에서 또 정의할 필요가 없다.
4) 다형성  
   다형성은 형태가 같지만 다른 기능을 하는 것을 말한다.  
   예를 들어 고양이 클래스에 '울음'이라는 속성이 정의되어 있다고 가정하자. 고양잇과인 사자가 고양이 클래스를 상속받을 때, 사자 클래스에도 '울음' 속성이 자동으로 추가된다.(상속)  
   하지만 사자 울음소리(크르릉)는 고양이(야옹)와 다르다. 이를 다형성이라고 한다.  
   <br/>

   부모 클래스로부터 상속을 받은 속성에 대해 자식 클래스에서 물려 받은 속성을 재정의할 수 있다. 이를 **오버라이딩**이라고 한다.  
   다형성을 사용하면 같은 이름의 속성을 유지함으로써 메서드 이름을 낭비하지 않는다.  
   예를 들어, 고양이와 사자의 울음소리를 호출하려면 각 객체에서 roar() 메서드를 호출하면 된다. roarCat(), roarLion()으로 나눠서 정의할 필요가 없어진다.  
   API가 많아질 수록 복잡성은 증가하기 때문에 다형성은 유용하다.  
<br/>

### 5) 객체지향을 쓰는 이유?
JAVA외에도 C++, C#, Python, Visual Basic, Swift 등 많인 언어에서 사용된다.  
객체지향은 절차지향의 후발주자이다. 즉 절차지향의 단점을 보완하고 편의성을 개선한 것이다.  
객체지향은 생산성과 유지보수 용이성을 높여, 개발자는 비교적 쉽고 빠르게 개발할 수 있다.  
<br/>

### 6) 장점
- 코드 재사용성  
   모듈화된 객체를 기반으로 코드를 작성하기 때문에 다른 로직에서 사용하거나 이미 만들어진 객체를 가져와 쓰기 용이하다.
- 간편한 유지보수  
  객체를 수정할 때, 해당 객체를 사용하는 모든 로직에 일괄적으로 적용돼 중복 코드 처리가 편리하다. 객체나 동작이 변경될 경우, 해당 객체나 동작과 연관된 객체만을 찾아 수정하면 된다.
- 큰 규모의 프로그래밍에 유리  
   객체, 모듈 단위로 구분되는 특징으로 인해 업무 분장이 쉽고 각 모듈의 연관성을 도식하기 쉽다.

### 7) 단점
- 비교적 느린 속도  
절차지향과 달리 각 객체의 의존 관계(결합도는 낮을 수록 좋음)로 인해 대체적으로 속도가 느리다.
- 높은 설계 역량 요구  
  모듈 단위의 상호작용으로 이루어진 방식이라 모듈의 정확한 명세와 상호 간 연관성이 얼마나 짜임새 있게 설계되었는지가 중요하다. 잘못 설계된 객체나 연관성은 라쟈나 코드(여러 주요 코드 레이어를 사용해 프로그램을 빌드하는 광범위한 코드 디자인)가 되기 쉽다.
- 코드의 잠재적 복잡성  
  높은 수준의 설계 역량과 더불어 추상 객체, 상속, 인터페이스 등의 복잡한 개념과 활용이 코드의 구조를 알아보기 어렵게 만든다.

### 8) 결합도
- Subclass Coupling(서브클래스 결합)  
  부모 클래스와 자녀 클래스의 관계에서 발생하는 경우. 자녀 클래스만 부모 클래스에 연결되는 단방향 관계 낮은 결합도 형태
- Temporal Coupling(일시적 결합)  
  두 개의 프로세스가 동시에 발생해서 하나의 모듈에 묶이는 경우  
<br/>

### 9) OOP의 5가지 설계 원칙
***SOLID***  

- SRP(Single Responsibility Principle, 단일 책임 원칙) : 클래스는 단 하나의 목적을 가져야 하고, 클래스를 변경하는 이유는 단 하나여야 한다.
- OCP(Open-Closed Principle, 개방 폐쇠 원칙) : 클래스는 확장에는 열려 있고, 변경에는 닫혀 있어야 한다.
- LSP(Liskov Substitution Principle, 리스코프 치환 원칙) : 상위 타입의 객체를 하위 타입으로 바꾸어도 프로그램은 일관되게 동작해야 한다.
- ISP(Interface Segregation Principle, 인터페이스 분리 원칙) : 클라이언트는 이용하지 않는 메소드에 의존하지 않도록 인터페이스를 분리해야 한다.
- DIP(Dependency Inversion Principle, 의존 역전 법칙) : 클라이언트는 추상화(인터페이스)에 의존해야 하며, 구체화(구현된 클래스)에 의존해선 안 된다.  
<br/>

### 10) 절차지향프로그래밍 vs 객체지향프로그래밍
- 절차지향프로그래밍  
  - 순차적 처리를 중요시하는 프로그래밍 기법이다.
  - 가장 대표적인 언어: C언어
  - 컴퓨터의 처리 구조와 유사해 실행 속도가 빠르다.
  - 코드의 순서가 바뀌면 동일한 결과를 보장하기 어렵다.
- 객체지향프로그래밍  
  - 실제 세계의 사물들을 객체로 모델링하여 개발을 진행하는 프로그래밍 기법이다.
  - 가장 대표적인 언어: Java
  - 캡슐화, 상속, 다형성 등과 같은 기법을 이용할 수 있다.
  - 절차지향 언어보다 실행 속도가 느리다.  

<br/>

#### 참고 링크
[OOP 개념](https://victorydntmd.tistory.com/117)  
[OOP란?](https://blog.itcode.dev/posts/2021/08/07/what-is-oop)