# REST 

### REST (Representational State Transfer)

: 웹(HTTP)의 장점을 활용한 아키텍처 

: <u>자원을 이름(표현)으로 구분</u> ➡ 해당 자원의 상태(정보) 를 주고 받는 모든 것을 의미

​        = 자원을 URI로 표시



⏩ <span style="color:red">자원(resource)의 표현(representation)</span>에 의한 <span style="color:red">상태 전달</span>

 	1. 자원의 표현
 	 - 자원 : 해당 소프트웨어가 관리하는 모~든 것 (e.g. 문서, 그림, 데이터, 소프트웨어 자체, ...)
 	 - 자원의 표현 : 그 자원을 표현하기 위한 이름 (e.g. DB의 학생 정보가 자원 → 'students' 표현)
 	2. 상태(정보) 전달
 	- 데이터가 요청되어지는 시점에서 자원의 상태(정보) 전달
 	- JSON 혹은 XML 을 통해 데이터를 주고 받는 것이 일반적

⇒ 하나의 URI는 하나의 고유한 리소스와 연결❗ 〰 화면에는 관심 없어❗

HTTP URI를 통해 제어할 자원(Resource) 명시하고, HTTP Method (GET, POST, PUT, DELETE)을 통해 해당 자원을 제어하는 명령을 내리는 방식의 아키텍처

: 자원을 이름으로 구분하고 해당 자원의 상태를 주고 받는 모든 것이 REST 이지만, 일반적으로 좁은 의미인 HTTP를 통해 CRUD를 실행하는 API를 뜻함

#### REST의 구성 요소

1. 자원 (Resource) : URI

   - 모든 자원에 고유한 ID 존재 & 자원은 서버에 존재
   - 자원을 구별하는 ID : '/groups/:group_id'와 같은 HTTP **URI**
   - Client는 URI를 이용해 자원 지정 → 해당 자원의 상태(정보)에 대한 조작을 Server에 요청

2. 행위 (Verb) : HTTP Method

   - HTTP 프로토콜 : GET, POST, PUT, DELETE 와 같은 메서드 제공

3. 표현 (Representation Resource)

   - Client가 자원의 상태(정보)에 대한 조작 요청 → Server는 이에 적절한 응답 (Representation) 보냄
   - REST에서 하나의 자원은 JSON, XML, TEXT, RSS 등 여러 형태의 표현으로 나타내어질 수 🙆‍♀️

   

   🤔<B> 기존 Service VS REST Service </B>

   ✔ 기존 Service

   요청에 대한 처리를 한 후 가공된 데이터를 이용하여 특정 플랫폼에 적합한 형태의 View를 만들어 반환

   ✔ REST Service

   데이터 처리만 하거나, 처리 후 반환할 데이터가 있다면 JSON이나 XML 형식으로 전달, View에 대해 신경 쓸 필요 ❌  ⏩ Open API에서 자주 사용

   

   ![Untitled.png (1440×433)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/de65ab6c-15f9-4739-955b-8180df8d2a02/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210719%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210719T150915Z&X-Amz-Expires=86400&X-Amz-Signature=0a18b864593e2226c8819f8bcc22b253579944d9886652ce2f18cd47b065a7d1&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

   ⇒ GET과 POST만으로 자원에 대한 CRUD 처리		⇒ 4가지 method를 모두 사용하여 CRUD 처리 

    & URI 는 액션을 나타냄             									& URI는 제어하려는 자원을 뜻함

   

   ![Untitled.png (1440×433)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/d47c314d-48fd-44af-8c5f-2efb3c7b4476/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210719%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210719T150950Z&X-Amz-Expires=86400&X-Amz-Signature=2817f61537846bb00e651760042a3a4c900fd53360a81c8ee0fd16bf8d7ee545&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)                             

   

   

   

   #### REST 특징

   1. Server-Client(서버-클라이언트 구조)
   
      - 자원이 있는 쪽이 Server, 자원을 요청하는 쪽이 Client
   
        - REST Server : API를 제공하고 비즈니스 로직 처리 및 저장을 책임짐
        - Client : 사용자 인증 관련 일을 직접 관리하고 책임짐

        ⇒ 서로 간 의존성이 줄어듦

   2. Stateless (무상태)

      - HTTP 프로토콜 : Stateless Protocol ⇒ REST 역시 무상태성
   
      - Client의 context를 서버에 저장 ❌ → 즉, 세션과 쿠키와 같은 context 정보를 신경 ❌ ⇒ 구현이 단순해짐

      - Server는 각각의 요청을 완전히 별개의 것으로 인식 & 처리
        - 각 API 서버 : Client의 요청만을 단순히 처리 ⇒ 요청 간의 연관 ❌
        - 서버의 처리 방식에 일관성을 부여하고 부담이 줄어듦 & 서비스의 자유도 ⏫

   3. Cacheable (캐시 처리 가능)

      - 웹 표준 HTTP 프로토콜을 그대로 사용하므로 웹에서 사용하는 기존의 인프라를 그대로 활용할 수 ⭕

      - HTTP가 가진 가장 강력한 특징 중 하나인 캐싱 기능 적용 가능

      - 캐시 : 대량의 요청을 효율적으로 처리 가능

      - 캐시 사용을 통해 응답시간이 빨라지고 REST Server 트랜잭션이 발생 ❌ → 전체 응답시간, 성능, 서버의 자원 이용률 향상 가능

   4. Layered System (계층화)
   
      - Client는 REST API Server만 호출
   
      - REST Server 는 다중 계층으로 구성
        - API Server는 순수 비즈니스 로직 수행 & 그 앞단에 보안, 로드밸런싱, 암호화, 사용자 인증 등을 추가하여 구조 상의 유연성을 줄 수 🙆‍♀️
        - 로드밸런싱, 공유 캐시 등을 통해 확장성 & 보안성 향상 가능
        - PROXY, 게이트웨이 같은 네트워크 기반의 중간 매체 사용 가능
   
   5. Code-On-Demand(optional)
      - Server로부터 스크립트를 받아서 Client에서 실행
   
   6. Uniform Interface (인터페이스 일관성)
      - URI로 지정한 Resource에 대한 조작 통일 & 한정적인 인터페이스로 수행
      - HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용 가능
        - 특정 언어나 기술에 종속 ❌



### REST API (Representational State Transfer API)

: REST 기반으로 서비스 API를 구현한 것

REST API 특징

- 시스템 분산 → 확장성 & 재사용성 ⏫ ⇒ 유지보수 및 운용 편리하게 ❗
- REST : HTTP 표준 기반으로 구현 ⇒ HTTP 지원하는 프로그램 언어로 클라이언트, 서버 구현 가능

⇒ REST API 제작 : JAVA, C#, 웹 등을 이용해 클라이언트 제작 가능



### RESTful

: 'REST API'를 제공하는 웹서비스를 'RESTful'하다고 표현

: REST를 REST답게 쓰기 위한 방법 → 누군가가 공식적으로 발표한 것 ❌

⇒ REST 원리를 따르는 시스템 : RESTful

RESTful의 목적

- 이해하기 쉽고 사용하기 쉬운 REST API를 만드는 것
- RESTful한 API 구현하는 근본 목적 : 성능 향상이 아닌 일관적인 컨벤션을 통한 API의 이해도 및 호환성을 높이는 것이 주 목적 (성능이 주 목적이라면 굳이 RESTful한 API 구현할 필요 ❌)

RESTful하지 못한 경우

e.g.

- CRUD 기능을 모두 POST로만 처리하는 API
- route에 resource, id 외의 정보가 들어가는 경우(/students/updateName)