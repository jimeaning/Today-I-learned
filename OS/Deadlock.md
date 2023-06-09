# 교착상태

두 개 이상의 프로세스나 스레드가 서로 자원을 얻지 못해서 다음 처리를 하지 못하는 상태. 무한히 다음 자원을 기다리는 상태.  
시스템적으로 한정된 자원을 여러 곳에서 사용하려고 할 때 발생 (마치 외나무 다리의 양 끝에서 서로가 비켜주길 바라는 것과 같음)  
<br/>

### 1) 교착상태 발생의 필요 충분 조건
교착상태가 발생하기 위해서는 네 가지 조건이 필요하다. 네 가지 조건 중 하나라도 충족되지 않으면 교착상태가 발생하지 않는다.  

- 상호배제(Mutual Exclusion) : 자원은 한번에 한 프로세스만 사용할 수 있다.
- 점유와 대기 (Hold and Wait) : 최소한 하나의 자원을 점유하고 있으면서 다른 프로세스에 할당되어 사용되고 있는 자원을 추가로 점유하기 위해 대기하는 프로세스가 있어야 한다.
- 비선점 (Non-preemption) : 다른 프로세스에 할당된 자원은 사용이 끝날 때까지 강제로 빼앗을 수 없어야 한다.
- 환형 대기 (Circular Wait) : 프로세스의 집합에서 순환 형태로 자원을 대기하고 있어야 한다. 공유 자원과 공유 자원을 사용하기 위해 대기하는 프로세스들이 원형으로 구성되어 있어 자신에게 할당된 자원을 점유하면서 앞이나 뒤에 있는 프로세스의 자원을 요구해야 한다.  

<br/>

### 2) 교착상태 처리

#### 예방 (Prevention)
교착상태 예방 기법은 교착상태가 발생하지 않도록 사전에 시스템을 제어하는 방법이다. 교착상태 발생의 네 가지 조건 중 어느 하나를 제거함으로써 수행된다. 자원 낭비가 가장 심한 기법이다.
- 상호 배제 부정: 한번에 여러 개의 프로세스가 공유 자원을 사용할 수 있도록 한다.
- 점유 및 대기 부정: 프로세스가 실행되기 전 필요한 모든 자원을 할당한다. 그래서 프로세스 대기를 없애거나 자원이 점유되지 않은 상태에서만 자원을 요구하도록 한다.
- 비선점 부정: 자원을 점유하고 있는 프로세스가 다른 자원을 요구할 때 점유하고 있는 자원을 반납하고, 요구한 자원을 사용하기 위해 기다리게 한다.
- 환형 대기 부정: 자원을 선형 순서로 분류하여 고유 번호를 할당하고, 순서대로 자원을 요구한다.  

<br/>

#### 회피 (Avoidance)
교착상태 회피 기법은 교착상태가 발생할 가능성을 배제하지 않고 교착상태가 발생하면 적절히 피해나가는 방법이다. 주로 은행원 알고리즘이 사용된다.  

**은행원 알고리즘**
1. 은행원 알고리즘은 다익스트라가 제안한 기법으로, 은행에서 모든 고객의 요구가 충족되도록 현금을 할당하는 데서 유래했다.
2. 각 프로세스에게 자원을 할당하여 교착상태가 발생하지 않고 모든 프로세스가 완료될 수 있는 상태를 안전상태, 교착상태가 발생할 수 있는 상태를 불안전 상태라고 한다.
3. 은행원 알고리즘을 적용하기 위해서는 자원의 양과 사용자(프로세스)수가 일정해야 한다.
4. 은행원 알고리즘은 프로세스의 모든 요구를 유한한 시간 안에 할당하는 것을 보장한다.  

<br/>

### 3) 교착상태 탐지 & 회복
교착상태가 되도록 허용한 다음 회복시키는 방법

#### 발견 (Detection)
교착상태 발견 기법은 시스템에 교착상태가 발생했는지 점검하여 교착상태에 있는 프로세스와 자원을 발견하는 것이다.  
교착상태 발견 알고리즘과 자원 할당 그래프 등을 사용할 수 있다.  
자원 요청 시 발견 알고리즘을 실행시켜 그에 대한 오버헤드를 발생한다.  

<br/>

#### 회복 (Recovery)
교착상태 회복 기법은 교착상태를 일으킨 프로세스를 종료(**프로세스 종료**)하거나 교착상태의 프로세스에 할당된 자원을 선점하여 프로세스나 자원을 회복(**자원 선점**)하는 것이다.  
#### 프로세스 종료
교착상태에 있는 프로세스를 종료하는 것으로, 교착상태에 있는 모든 프로세스를 종료하는 방법과 교착상태에 있는 프로세스들을 하나씩 종료해가며 교착상태를 해결하는 방법이 있다.  
#### 자원선점
교착상태의 프로세스가 점유하고 있는 자원을 선점하여 다른 프로세스에게 할당하며 해당 프로세스를 일시 정지하는 방법이다. 우선순위가 낮은 프로세스, 수행된 정도가 적은 프로세스, 사용되는 자원이 적은 프로세스 등을 위주로 해당 프로세스의 자원을 선점한다.  
**자원 선점 시 고려사항**  
1. 자원을 선점할 프로세스 선택 문제: 최소의 피해를 줄 수 있는 프로세스를 선택한다.
2. 자원을 선점한 프로세스의 복귀 문제: 자원이 부족한 상태이므로 대부분 일시 중지시키고 다시 시작하는 방법을 사용한다.
3. 기아 현상 문제: 한 프로세스가 계속하여 자원 선점 대상이 되지 못하도록 고려해야 한다.  

<br/>

### 4) 기아상태를 설명하는 식사하는 철학자 문제
교착상태 해결법  
1. n명이 앉을 수 있는 테이블에 n-1명만 앉힌다.
2. 한 철학자가 젓가락 두 개를 모두 집을 수 있는 상황에서만 젓가락을 집도록 허용한다.
3. 누군가는 왼쪽 젓가락을 먼저 집지 않고 오른쪽 젓가락을 먼저 집도록 허용한다.

<br/>


#### 참고
[교착상태란?-티스토리](https://coding-factory.tistory.com/311)  
[데드락](https://gyoogle.dev/blog/computer-science/operating-system/DeadLock.html)