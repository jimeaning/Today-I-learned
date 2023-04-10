# RESTful API  

### 1) REST (Representational State Transfer)
자원을 이름으로 구분해 해당 자원의 상태를 주고 받는 모든 것을 의미한다. 즉, 자원의 표현에 의한 상태 전달이다.
  - 자원: 해당 소프트웨어가 관리하는 모든 것 (문서, 그림, 데이터, 해당 소프트웨어 자체 등)
  - 자원의 표현: 그 자원을 표현하기 위한 이름 (DB의 학생 정보가 자원일 때, 'student'는 자원의 표현)  
  - 상태(정보) 전달: 데이터가 요청되어지는 시점에서 자원의 상태(정보) 전달. JSON 혹은 XML을 통해 데이터를 주고 받는 것이 일반적
    
월드 와이드 웹(www)과 같은 분산 하이퍼미디어 시스템을 위한 소프트웨어 개발 아키텍처의 한 형식이다. REST는 기본적으로 웹의 기존 기술과 HTTP 프로토콜을 그대로 활용하기 때문에 웹의 장점을 최대한 활용할 수 있는 아키텍처 스타일이다. REST는 네트워크 상에서 Client와 Server 사이의 통신 방식 중 하나이다.  

 REST는 처음에 인터넷과 같은 복잡한 네트워크에서 통신을 관리하기 위한 지침으로 만들어졌다. REST 기반 아키텍처를 사용해 대규모의 고성능 통신을 안정적으로 지원할 수 있다. 쉽게 구현하고 수정이 가능해 모든 API 시스템을 파악하고 여러 플랫폼에서 사용할 수 있다.  
1. HTTP URI(Uniform Resource Identifier)를 통해 자원(Resource)을 명시하고
2. HTTP Method(POST, GET, PUT, DELETE, PATCH 등)를 통해
3. 해당 자원(URI)에 대한 CRUD Operation을 적용하는 것이다.  
<br/>

### 2) REST 구성 요소
1. 자원(Resource) : HTTP URI
   - 모든 자원에 고유한 ID가 존재하고 이 자원은 서버에 존재한다.
   - 자원을 구별하는 ID는 '/groups/:group_id'와 같은 HTTP URI이다.
   - Client는 URI를 이용해 자원을 지정하고 해당 자원의 상태(정보)에 대한 조작을 서버에 요청한다.
2. 자원에 대한 행위(Verb) : HTTP Method  
   - HTTP 프로토콜의 Method를 사용한다.
   - HTTP 프로토콜은 GET, POST, PUT, DELETE와 같은 메소드를 제공한다.
3. 자원에 대한 행위의 내용(Representations) : HTTP Message Pay Load  
   - 클라이언트가 자원의 상태(정보)에 대한 조작을 요청하면 서버는 이에 대한 적절한 응답을 보낸다.
   - REST에서 하나의 자원은 JSON, XML, TEXT, RSS 등 여러 형태의 응답을 가질 수 있다.
   - JSON이나 XML을 통해 데이터를 주고 받는 것이 일반적이다.  
<br/>

### 3) REST 특징
1. Server-Client(서버-클라이언트 구조)  
   - 자원이 있는 쪽이 서버, 요청하는 쪽이 클라이언트이다.  
     - REST Server: API를 제공하고 비즈니스 로직 처리 및 저장을 책임진다.
     - 사용자 인증이나 context(세션, 로그인 정보) 등을 직접 관리하고 책임진다.
   - 서로 간 의존성이 줄어든다.
2. Stateless(무상태)  
   REST 아키텍처에서 무상태는 서버가 이전 모든 요청과 독립적으로 모든 클라이언트 요청을 완료하는 통신 방법이다.
   - HTTP 프로토콜은 Stateless Protocol이므로 REST 역시 무상태성을 갖는다.
   - 클라이언트의 context를 서버에 저장하지 않는다.
   - 서버는 각각의 요청을 완전히 별개의 것으로 인식하고 처리한다.
     - 각 API 서버는 클라이언트의 요청만을 단순 처리한다. 
     - 즉 이전 요청이 다음 요청 처리에 연관되어서는 안 된다.
     - 물론 이전 요청이 DB를 수정하여 DB에 의해 바뀌는 것은 가능하다. 
     - 서버의 처리 방식에 일관성을 부여하고 부담이 줄여들며 서비스의 자유도가 높아진다.
1. Cacheable(캐시 처리 기능)  
   - 웹 표준 HTTP 프로토콜을 그대로 사용하므로 웹에서 사용하는 기존 인프라를 그대로 활용할 수 있다. 즉 HTTP가 가진 가장 강력한 특징 중 하나인 캐싱 기능을 적용할 수 있다. Last-Modified 태그나 E-Tag를 사용하면 캐싱 구현이 가능하다.
   - 대량의 요청을 효율적으로 처리하기 위해 캐시가 요구된다.
   - 캐시 사용을 통해 응답시간이 빨라지고 REST 서버 트랜잭션이 발생하지 않기 때문에 전체 응답시간, 성능, 서버의 자원 이용률을 향상시킬 수 있다.
2. Layered System(계층화)  
   - 클라이언트는 REST API 서버만 호출한다.
   - REST 서버는 다중 계층으로 구성될 수 있다. API 서버는 순수 비즈니스 로직을 수행하고, 그 앞단에 보안, 로드밸런싱, 암호화, 사용자 인증 등을 추가해 구조적 유연성을 줄 수 있다. 또한 로드밸런싱, 공유 캐시 등을 통해 확장성과 보안성을 향상시킬 수 있다.
   - PROXY, 게이트웨이 같은 네트워크 기반 중간 매체를 사용할 수 있다.
   
3. Uniform Interface(인터페이스 일관성)
   - URI로 지정한 리소스에 대한 조작을 통일되고 한정적인 인터페이스로 수행한다.
   - HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다. 특정 언어나 기술에 종속되지 않는다.   
<br/>

### 4) REST의 장단점
**장점**  
1. HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구축할 필요 없다.
2. HTTP 프로토콜의 표준을 최대한 활용해 여러 추가적 장점을 함께 지닌다.
3. HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
4. Hypermedia API의 기본을 충실히 지키면서 범용성을 보장한다.
5. REST API 메시지가 의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있다.
6. 여러가지 서비스 디자인에서 생길 수 있는 문제를 최소화한다.
7. 서버와 클라이언트의 역할을 명확하게 분리한다.  
   
**단점**  
1. 표준이 존재하지 않아 정의가 필요하다.
2. HTTP Method 형태가 제한적이다.
3. 브라우저를 통해 테스트할 일이 많은 서버라면 쉽게 고칠 수 있는 URL보다 Header 정보의 값을 처리해야 하므로 전문성이 요구된다.  
4. 구형 브라우저에서 호환이 되지 않아 지원하지 못하는 동작이 많다.(익스폴로어)  
   <br/>

### 5) API
Application Programming Interface. 다른 소프트웨어 시스템과 통신하기 위해 따라야 하는 규칙이다.  
<br/>
**클라이언트**  
클라이언트는 웹에서 데이터에 액세스하려는 사용자이다. 클라이언트는 API를 사용하는 사람 혹은 소프트웨어 시스템일 수 있다. 예를 들어, 날씨 시스템에서 날씨 데이터에 접근하는 프로그램이 될 수 있다. 혹은 사용자가 날씨 웹 사이트를 직접 방문할 때 동일한 데이터를 액세스할 수 있다.  
**리소스**  
리소스는 다양한 애플리케이션이 클라이언트에게 제공하는 정보이다. 리소스는 이미지, 동영상, 텍스트, 숫자 또는 모든 유형의 데이터가 가능하다. 클라이언트에 리소스를 제공하는 시스템을 서버라고 한다. 조직은 API를 이용하여 리소스를 공유하고 보안, 제어 및 인증을 유지하면서 웹 서비스를 제공한다. 또한 API는 특정 내부 리소스에 액세스할 수 있는 클라이언트를 결정하는데 도움이 된다.  
<br/>

### 6) REST API  
REST 기반으로 서비스 API를 구현한 것.  
최근 OpenAPI(누구나 사용할 수 있도록 공개된 API: 구글 맵, 공공 데이터 등), 마이크로 서비스(하나의 큰 애플리케이션을 여러 개 작은 애플리케이션으로 쪼개어 변경과 조합이 가능하도록 만든 아키텍처) 등을 제공하는 업체 대부분은 REST API를 제공한다.  
<br/>

### 7) REST API 설계 예시
1. URI는 동사보다 명사를, 대문자보다는 소문자를 사용해야 한다.  
   >Bad: ~/jimeaning/Running  
   >Good: ~/jimeaning/run
2. 마지막에 슬래시(/)를 포함하지 않는다.
   >Bad: ~/jimeaning/test/  
   >Good: ~/jimeaning/test
3. 언더바 대신 하이픈을 사용한다.
   >Bad: ~/jimeaning/test_blog   
   >Good: ~/jimeaning/test-blog
4. 파일확장자는 URI에 포함하지 않는다.
   >Bad: ~/jimeaning/photo.jpg  
   >Good: ~/jimeaning/photo
6. 행위를 포함하지 않는다.
   >Bad: ~/jimeaning/delete-post/1  
   >Good: ~/jimeaning/post/1   

<br/>

### 8) REST API의 특징 
- 사내 시스템들도 REST 기반으로 시스템을 분산해 확장성과 재사용성을 높여 유지보수 및 운용을 편리하게 할 수 있다.
- REST는 HTTP 표준을 기반으로 구현하므로, HTTP를 지원하는 언어로 클라이언트, 서버를 구현할 수 있다.
- REST API를 제작하면 델파이 클라이언트 뿐만 아니라 자바, C#, 웹 등을 이용해 클라이언트를 제작할 수 있다.  
<br/>

### 9) RESTful
RESTful은 일반적으로 REST라는 아키텍처를 구현하는 웹 서비스를 나타내기 위해 사용되는 용어이다. REST 원리를 따르는 시스템을 RESTful이라고 한다.  
<br/>

### 10) RESTful 목적
- 이해하기 쉽고 사용하기 쉬운 REST API를 만드는 것
- RESTful한 API를 구현하는 근본적인 목적은 성능 향상이 아니라 일관적인 컨벤션을 통한 API의 이해도 및 호환성 높이기이다. 성능이 중요한 상황에서는 굳이 RESTful한 API를 구현할 필요 없다.  
<br/>

### 11) RESTful 하지 못한 경우
1) CRUD 기능을 모두 POST로만 처리하는 API
2) route에 resource, id 외의 정보가 들어가는 경우 (/students/updateName)  
<br/>

### 12) RESTful API
RESTful API는 두 컴퓨터 시스템이 인터넷을 통해 정보를 안전하게 교환하기 위해 사용하는 인터페이스이다. RESTful이란 REST의 원리를 따르는 시스템을 의미한다. 하지만 REST를 사용했다고 모두 RESTful한 것은 아니다. REST API 설계 규칙을 올바르게 지킨 시스템을 RESTful하다고 말할 수 있다. 모든 CRUD 기능을 POST로 처리하는 API, URI 규칙을 올바르게 지키지 않은 API는 REST API를 사용해도 RESTful하지 못한 시스템이다.  
<br/>

### 13) RESTful API 이점
- 확장성
- 유연성
- 독립성  
<br/>


### 참고
[RESTful API란-aws](https://aws.amazon.com/ko/what-is/restful-api/)  
[REST API-tistory](https://khj93.tistory.com/entry/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-REST-API%EB%9E%80-REST-RESTful%EC%9D%B4%EB%9E%80)  
[REST, REST API, RESTful](https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html)