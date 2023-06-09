# 추상클래스와 인터페이스

클래스는 일반 클래스와 추상 클래스로 나뉜다. 추상 클래스는 클래스 내 추상 메소드가 하나 이상 포함되거나 abstract로 정의된 경우를 말한다.  
반면 인터페이스는 모든 메소드가 추상 메소드이다.  

추상 클래스와 인터페이스는 존재 목적이 다르다. 추상 클래스는 해당 추상 클래스를 상속받아 기능을 이용하고, 확장시키는 데 있다.  
반면 인터페이스는 함수의 껍데기만 있다. 이는 함수의 구현을 강제하기 위해서이다. 구현을 강제함으로써 구현 객체의 같은 동작을 보장한다.  

자바는 다중 상속을 허용하지 않는다. 다중 상속의 모호성 때문이다. 하지만 다중 상속의 이점을 포기할 수 없어 인터페이스를 사용한다.

<br>

### 추상 클래스 (Abstract Class)
- 단일 상속을 지원한다
- 변수를 가질 수 있다
- 하나 이상의 abstract 메소드가 존재해야 한다.
- 자식 클래스에서 상속을 통해 abstract 메소드를 구현한다 (extends)
- abstract 메소드가 아닌 구현된 메소드를 상속받을 수 있다.

추상 클래스는 일반 클래스와 별 다를 것이 없다. 다만 추상 메서드를 선언하여 상속을 통해서 자손 클래스에서 완성하도록 유도하는 클래스이다. 그래서 미완성 설계도라고도 표현한다.  
**상속을 위한 클래스이기 때문에 따로 객체를 생성할 수 없다.**  

<br>

```
abstract class 클래스이름 {
    ...
    public abstract void 메서드이름();
}
```

<br>

### 인터페이스 (Interface)
- 다중 상속을 지원한다
- 변수를 가질 수 없다. 상수는 가능하다.
- 모든 메소드는 선언부만 존재한다.
- 구현 클래스는 선언된 모든 메소드를 overriding 한다.

추상 클래스가 미완성 설계도라면, 인터페이스는 기본 설계도이다. 인터페이스도 추상클래스처럼 다른 클래스를 작성하는데 도움을 주는 목적으로 작성하고, 클래스와 다르게 다중상속(구현)이 가능하다.  

<br>

```
interface 인터페이스이름 {
    public static final 상수이름 = 값;
    public abstract void 메서드이름();
}
```
<br>

### 추상 클래스와 인터페이스의 차이점
둘의 공통점은 추상 메서드를 사용할 수 있다는 것이다.

1. 사용 의도 차이점

**추상 클래스는 IS - A "~이다"  
인터페이스는 HAS - A "~을 할 수 있는"**

이렇게 구분하는 이유는 다중 상속 가능 여부에 따라 용도를 정한 것이다. 자바 특성 상 한 개의 클래스만 상속이 가능하여 해당 클래스의 구분을 추상 클래스 상속을 통해 해결하고, 할 수 있는 기능들은 인터페이스로 구현한다.

2. 공통된 기능 사용 여부

만약 모든 클래스가 인터페이스를 사용해서 기본 틀을 구성하면 고통으로 필요한 기능들도 모든 클래스에서 오버라이딩하여 재정의 해야 하는 번거로움이 있다. 이렇게 공통된 기능이 필요하다면 추상 클래스를 이용해서 일반 메서드를 작성한 후 자식 클래스에서 사용하도록 하면 된다.  
만약 각각 다른 추상 클래스를 상속하는데 공통된 기능이 필요하면, 해당 기능을 인터페이스로 작성해서 구현한다.

<br>


### Java 버전에 따른 기능
Java 버전이 올라 갈수록 abstract의 기능을 interface가 흡수한다.
- java8: inteface에서 default method 사용 가능
- java9: interface에서 private method 사용 가능

<br>

#### 참고
[자바의 추상클래스와 인터페이스-브런치](https://brunch.co.kr/@kd4/6)  
[추상클래스와 인터페이스 차이는?](https://gyoogle.dev/blog/interview/%EC%96%B8%EC%96%B4.html#%E1%84%8E%E1%85%AE%E1%84%89%E1%85%A1%E1%86%BC-%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B3%E1%84%8B%E1%85%AA-%E1%84%8B%E1%85%B5%E1%86%AB%E1%84%90%E1%85%A5%E1%84%91%E1%85%A6%E1%84%8B%E1%85%B5%E1%84%89%E1%85%B3-%E1%84%8E%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%82%E1%85%B3%E1%86%AB)  
[추상클래스와 인터페이스 차이점 예제로-티스토리](https://myjamong.tistory.com/150)