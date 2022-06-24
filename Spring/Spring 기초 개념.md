## Spring Framework
자바 객체를 담고 직접 관리하는 경량 컨테이너이다. 객체의 생성, 소멸, 라이프사이클을 관리하고, Spring으로부터 필요한 객체를 가져와 사용가능하다.



## IOC (Inversion of Control)
제어의 역전이라는 뜻으로, 사용자가 제어의 흐름을 컨트롤 하지 않고 특정 객체에 제어 권한을 전부 위임한다.


###  IOC의 구성요소

#### - DL(Dependency Lookup)
의존성 검색이라는 뜻으로 컨테이너에서 제공하는 API를 이용해 빈을 검색하는 방법이다.

#### - DI(Dependency Injection)
의존성 주입이라는 뜻으로, 클래스 사이에 필요로 하는 의존관계를 빈 설정 정보를 통해 자동으로 연결한다.

## POJO(Plain Old Java Object) 
평범한 자바 오브젝트라는 뜻으로, 객체지향적인 원리에 충실해야한다는 것을 의미한다. 
이것을 사용함으로서 코드가 심플해지고, 테스트하기 편해진다.

## AOP(Aspect Oriented Programming)
관점 지향 프로그래밍이라는 뜻으로, 중복된 코드들을 한 곳에 모아 중복되는 코드를 제거하고, 공통 기능을 가진 코드를 작성한다.
유지보수성과  재활용성이 높아진다.

## Model
Data처리를 담당하고, Service와 DAO영역으로 나누어진다. View와 Controller의 정보를 가지면 안된다.

## View
사용자 interface를 담당하고, Controller를 통해 받은 데이터에 대한 시각화를 한다. Controller의 정보만 알고 있어야 한다.

## Controller
View의 요청을 Model에 전달하고, Model의 결과를 View로 전달한다. 요청에러와 모델 에러를 처리하고, View와 Model의 정보를 알아야한다.

## Spring Framework의 구조

![Spring Framework 구조](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Ft1.daumcdn.net%2Fcfile%2Ftistory%2F99A523405B9E2C1510)

### Spring Core
Spring Container를 의미합니다. Container중에 IOC를 적용하는 Bean Factory Container가 핵심이다.

### Spring Context
bean을 포함하여 여러 기능을 가진 공간
1) Root-Context : 모든 서블릿이 공유가능한 Bean이 위치하는 공간이다. (ex. Repository, Service)
2) Servlet-Context : 개별 서블릿의 Bean이 위치하는 공간이다. (ex. Controller)

### Spring DAO
Data Access Object의 약자로 Data에 접근하는 객체이다.

### Spring ORM
Ojbect Relational Mapping의 약자로 객체와의 관계 설정을 하는 것이다. Ibatis, Hibernate, JDO등 객체 관계형 도구(OR도구)를 사용할 수 있도록 지원한다.

### Spring AOP
AOP를 적용 할 수 있게 도와주는 Module이다.

### Spring Web
기본적인 웹기반 통합 기능들을 제공한다. (ex. multipart기능, servlet listener를 사용한 context 초기화, 웹-기반 어플리케이션 컨텍스트)

### Spring MVC
Model2 구조로 application을 만들 수 있도록 지원한다.


</br></br></br>
---

###### 참조자료
- https://khj93.tistory.com/entry/Spring-Spring-Framework%EB%9E%80-%EA%B8%B0%EB%B3%B8-%EA%B0%9C%EB%85%90-%ED%95%B5%EC%8B%AC-%EC%A0%95%EB%A6%AC
- http://ldg.pe.kr/framework_reference/spring/ver1.2.2/html_single/index.html
- https://velog.io/@seculoper235/Spring-Core-Context-1%ED%8E%B8
