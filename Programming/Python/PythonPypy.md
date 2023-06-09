# Python3와 PyPy3


### 🤖 컴파일러 언어 vs 인터프리터 언어
**컴파일 언어**

개발자가 작성한 소스코드를 모두 기계어로 변환한 후 기계(JVM과 같은 가상머신)에 넣고 기계어 코드를 실행한다. 소스코드를 기계어로 컴파일하는 과정에서는 인터프리터 언어에 비해 시간이 소요되지만 런타임 상황에서는 이미 기계어로 모든 소스코드가 변환되어 있기 때문에 빠르게 실행할 수 있다.

종류 : C, C++, C#, Java 등  
빌드 과정 : 소스 파일 -> (컴파일) -> 오브젝트 파일 -> (링킹) -> 실행 파일

![](https://velog.velcdn.com/images/jimeaning/post/af205cc2-354a-46a9-bb0b-c88f46c51d17/image.png)


**인터프리터 언어**

한 줄 씩 읽고 바로 명령어를 실행하는 언어이다. 런타임 상황에서는 한 줄 씩 실시간으로 읽어서 실행하기 때문에 컴파일 언어에 비해 속도가 느리다. 실행 속도는 느리지만 코드 변경 시 빌드 과정 없이 바로 실행이 가능하다는 장점이 있다.

종류 : R, Python, Ruby, SQL, JavaScript 등

![](https://velog.velcdn.com/images/jimeaning/post/005660b4-5838-4b2e-979b-c3ee745596e6/image.png)


**🎱 차이점**
1. 실행 단계의 차이  
   컴파일 언어는 '컴파일러' 단계가 필요하고, 인터프리터 언어는 별도의 컴파일러 과정이 필요하지 않다.
2. 생산 속도의 차이  
   컴파일 언어는 '컴파일' 과정이 들어가기 때문에 인터프리터 언어보다 생산 속도가 느리다. 인터프리터 언어는 과정이 단순해 생산 속도가 빠르다.
3. 실행 속도의 차이  
   실행 속도는 컴파일러 언어가 더 빠르다. 컴파일을 한 뒤 생성된 파일에 대해 프로그램이 실행되기 때문에 실시간으로 읽고 수행되는 인터프리터 언어에 비해 훨씬 빠르다.


<br>

### 🤖 Python3

Python과 C로 구성된 언어로 구현체가 CPython이다. 즉, Python3는 인터프리터이면서 컴파일러 언어이다. 개발자가 작성한 Python 코드를 컴파일하여 bytecode로 바꾸고 인터프리터가 실행된다.

<br>

### 🤖 PyPy3

Python3 언어와 문법은 같지만 JIT(Just-In Time) 컴파일 방식을 도입하였다. JIT 컴파일이란 프로그램을 실행하기 전에 컴파일하는 대신, 프로그램을 실행하는 시점에서 필요한 부분을 즉석으로 컴파일 하는 방식이다. 자주 쓰이는 코드를 캐싱하는 기능이 있어 인터프리터 언어의 느린 실행 속도를 개선할 수 있다.


<br>

### 🤖 정리

간단한 코드 상에서는 Python3가 메모리, 속도 측면에서 우세할 수 있고, 복잡한 코드(반복)를 사용하는 경우에는 PyPy3이 우세하다.

코드 상황에 맞추어 두 구현체를 적절히 사용하는 것이 효율적이다.

<br>

### 🤖 백준 문제
[2573_빙산](https://www.acmicpc.net/problem/2573)  
[1062_가르침](https://www.acmicpc.net/problem/1062)

<br>

#### 참고
[Python3 와 PyPy3 차이](https://ralp0217.tistory.com/entry/Python3-%EC%99%80-PyPy3-%EC%B0%A8%EC%9D%B4)  
[백준 문제로몸소 겪은 Python과 Pypy의 차이](https://imksh.com/46)  
[Python3 vs Pypy3](https://velog.io/@jeewoo1025/Python3-vs-Pypy3)