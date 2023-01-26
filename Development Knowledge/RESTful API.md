# RESTful이란?
-> REST 원리를 따르는 시스템을 RESTful하다고 말한다.
RESTful의 목적
-> 이해하기 쉽고, 사용하기 쉬운 REST API를 만들기 위해 사용된다.

## REST란?
-> Representational State Transfer의 약자로, 자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 것이다.
-> REST는 HTTP 프로토콜을 사용하기 때문에 웹의 장점을 활용할 수 있는 아키텍처 스타일이다.
-> 네트워크 상에서 client와 server간의 통신 방식 중 하나이다.
-> HTTP URI를 통해 자원을 명시하고, HTTP Method를 통해 해당 자원에 대한 CRUD Operation을 적용하는 것.

## REST의 장점
#### 1) HTTP 프로토콜의 인프라를 그대로 사용하므로 별도의 인프라 구축할 필요 X

#### 2) API 메시지를 이해하기 쉽다.

#### 3) Server와 Client의 역할을 분리한다. -> 각 프로그램에서의 변경이 서로에게 영향을 주지 않는다.

#### 4) 다양한 언어와 플랫폼으로  서버와 클라이언트를 작성할 수 있다.

## REST의 단점
#### 1) 사용할 수 있는 메소드가 4가지로, 형태가 제한적이다.

#### 2) 구형 브라우저가 제대로 지원해주지 못한다. (PUT, DELETE 사용 X, pushState 지원 X)

#### 3) 오버패칭과 언더패칭 : 고정적인 데이터 구조를 전송하는 엔드포인트의 특성으로 인해 클라이언트에서 필요한 것보다 많은데이터를 전송하는 오버패칭과 필요한 데이터를 받기 위해 여러번의 API 호출을해야하는 언더패칭 문제 발생

#### 4) 엔드포인트 증가 : 서비스가 복잡해 질 수록 클라이언트에서 요청하는 데이터 역시 증가하므로 관리해야하는 엔드포인트가 증가


## REST 사용 이유
1) 어플리케이션 분리 및 통합
2) 멀티 플랫폼에서 통신 가능하다.

## REST 구성 요소
### 1) URI (Uniform Resource Identifier)
- Client 는 URI를 이용해 자원 지정, Server에 해당 자원의 상태에 대한 조작을 요청.
### 2) HTTP Method (행위)
- GET, POST, PUT, DELETE
### 3) 표현 (Representation of Resource)
- JSON, XML, TEXT, RSS등의 형태로 표현.

## REST 특징
### 1. Server-Client
- Server : API를 제공하고 로직 처리 및 저장
- Client : 사용자 인증, Context(세션, 로그인 등)을 관리

### 2. Stateless(무상태)
- 각각의 요청을 별개의 것으로 처리.

### 3. Cacheable(캐시 처리 가능)
- HTTP의 강력한 특징인 캐싱 기능을 적용할 수 있다. (Last-Modified 태그 or E-Tag를 이용하여 캐싱 구현 가능)
- 대량의 요청을 효율적으로 처리
- 응답시간 ↑, 성능, 서버의 자원 이용률 ↑
> 캐싱 : RAM 같은 빠르게 액세스 가능한 하드웨어에 저장되며, 일시적인 데이터를 저장하는 고속 데이터 저장 계층이다.

### 4. Layered System(계층화)
- REST Server를 다중 계층으로 구성하여 확장성, 보안성 ↑
- API Server 앞단에 보안, 로드밸런싱, 암호화, 사용자 인증, 공유 캐시를 추가 가능.
- PROXY, 게이트웨이 같은 네트워크 기반의 매체 사용 가능
> 로드밸런싱 : 서버가 받는 요청을 여러 대의 서버로 나누어 처리하는 것.

### 5. Code-On-Demand(optional)
- Server로부터 스크립트를 받아 Client에서 실행.
- 반드시 충족할 필요 X

### 6. Uniform Interface(인터페이스 일관성)
- 특정 언어나 기술에 종속 X


## REST API 설계 규칙
- 동사 X, 명사 O
- 대문자 X, 소문자 O
-  언더바(_) X, 하이픈(-) O
- /로 끝내기 X


## 응답 상태 코드
1xx : 전송 프로토콜 수준의 정보 교환
2xx : 클라이언트 요청이 성공적으로 수행됨
3xx : 클라이언트는 요청을 완료하기 위해 추가적인 행동을 취해야함
4xx : 클라이언트의 잘못된 요청
5xx : 서버쪽 오류로 인한 상태코드


## API의 종류
### 1) SOAP(Simple Object Access Protocol)
보안이나 메시지 전송 등에서 많은 표준이 정해져 있어서 복잡 / 성공/반복 실행 로직이 규정되어 있어서 끝까지 신뢰성 제공.
ex) 많은 리소스와 보안, 多요구사항인 기업용 어플리케이션

### 2) REST(Representational state Transfer)
리소스에 대한 표현을통해 상태를 전송. 

### 3)  GraphQL
API를 위한 쿼리 언어이자 서버측 런타임으로, 단일 API 호출로 다양한 데이터 소스에서 데이터를 끌어오는 요청을 구성할 수 있다.
#### 장점
- 클라이언트는 오버페칭 없이 요청한 결과만 얻음
- 통신 오류 감소
- 기존 REST API에 추가하여 연동 가능 

#### 단점
- 캐싱이 REST 보다 훨씬 복잡
- 높은 러닝 커브 
- 서버측에서 데이터 쿼리의 작업을 하므로 서버 개발자 작업의 복잡성 ↑  

> 출처
> [RESTful API에 대하여](https://lietenant-k.tistory.com/108)
> [API란](https://velog.io/@kimscastle/%EB%B0%B1%EC%97%94%EB%93%9C-1%EC%9D%BC%EC%B0%A8-API%EB%9E%80-API-%EC%A2%85%EB%A5%98%EB%8A%94)
> [API란 개념,종류(REST API, SOAP API), 역사 쉽게정리](https://sac4686.tistory.com/23)
> [로드밸런싱](https://tecoble.techcourse.co.kr/post/2021-11-07-load-balancing/)
> [REST란?](https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html)
> [RESTful API란 무엇입니까?](https://aws.amazon.com/ko/what-is/restful-api/)
> [GraphQL이란?](https://www.redhat.com/ko/topics/api/what-is-graphql)
> 
