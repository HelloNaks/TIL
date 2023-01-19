<h1>OOP</h1>

<h2>OOP란?</h2>

> <h4>OOP란 Object Oriented Programming의 약자로, 객체 지향 프로그래밍이다. </h4>

 객체 지향 프로그래밍은 우리가 실생활에서 사용하는 모든 것을 **객체**라고 하며, 객체 지향 프로그래밍은 프로그램 구현에 필요한 객체를 파악하고 각각의 객체들의 역할이 무엇인지를 정의하여 객체들 간의 상호작용을 통해 프로그램을 만드는 것을 의미한다. 객체는 클래스라는 틀에서 생겨난 실체(instance)이다. 따라서 객체 지향 프로그램은 객체와 객체 간의 연결로 되어 있으며 각각의 객체안에 자료구조와 알고리즘이 들어있다.

## 절차 지향 vs 객체 지향
![절차 지향 vs 객체 지향](https://velog.velcdn.com/images%2F1205kjw%2Fpost%2Fe26e78cf-4b30-4862-9415-cc24f98e35b1%2Fimage.png)
> 절차 지향 vs 객체 지향
> 출처 : https://velog.io/@1205kjw/6.1.2-%EC%A0%88%EC%B0%A8%EC%A7%80%ED%96%A5%EA%B3%BC-%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-td8rfgpq

### 절차 지향
절차 지향 모델링은 프로그램을 기능 중심으로 바라보는 방식으로 "무엇을 어떤 절차로 할 것인가?"가 핵심이 된다. 즉, 어떤 기능을 어떤 순서로 처리하는가에 초점을 맞춘다.
ex) 베이직, C 언어

### 객체 지향
객체 지향 모델링은 기능이 아닌 객체가 중심이 되며, "누가 어떤 일을 할 것인가?"가 핵심이 된다. 즉, 객체를 도출하고 각각의 역할을 정의해 나가는 것에 초점을 맞춘다.
ex) C++, Java, Python, Swift

### 절차 지향 vs 객체 지향
- 절차 지향 : 소형 프로그래밍(객체 별로 나눌 때, 오히려 복잡해질 수 있다)
- 객체 지향 : 대형 프로그래밍(많은 역할을 객체로 묶을 수 있다)

## 객체 지향 언어의 특성
### 1. 캡슐화(Encapsulation)
- 객체를 캡슐로 싸서 내부를 보호하고 볼 수 없게 하는 것(정보은닉)
- 객체가 독립적인 역할을 할 수 있도록 데이터와 기능을 하나로 묶어 관리
- 메소드를 이용하여 외부와 상호작용
#### Java에서의 캡슐화
##### 접근제어자를 통한 설계 필요
- 클래스 접근 제어자
	- default : 동일 패키지의 class에만 인스턴스(객체) 생성 가능
	- public : 다른 패키지에서 인스턴스(객체) 생성 가능
- 메소드 접근 제어자
	- private : 동일 클래스 내에서만 접근 가능 (this를 사용하는 것들은 외부에서 접근 불가능, 상속X)
	- default : 접근제어자가 없는 형태로 동일한 패키지 내에서만 접근 가능
	- protected : 동일한 패키지 내에서 사용 가능, 다른 패키지라도 상속받은 클래스에 접근 가능
	- public : 모든 객체에서 접근 가능

### 2. 상속(Inheritance) 

![상속](http://www.tcpschool.com/lectures/img_java_inheritance_diagram.png)
> 상속
> 출처 : http://www.tcpschool.com/java/java_inheritance_concept
- 부모 개체의 속성(필드, 메소드)을 자식 개체에서 모두 물려받는 것을 의미
- 이미 작성된 클래스를 받아 새로운 클래스를 생성
- 기존 코드를 재사용
#### Java에서의 상속
##### extends : 자식 클래스 옆에 extends 키워드를 붙이고, 상속할 부모 클래스명을 적기
```Java
public class Car{
	String name; // 필드
	int price; 

	public void Print(){ // 메소드
		System.out.println("차의 이름과 가격 : "+name+" "+price);
	}
}

public class Audi extends Car{
	Audi(String name, int price){ // 생성자
		this.name = name;
		this.price = price;
	}
}

public static void main(String[] args){
	Audi audi = new Audi("Q7",20000);
	Audi.Print();
}
```
> [구현 결과] : 차의 이름과 가격 : Q7 20000
### 3. 추상화(Abstraction)
![추상화](https://t1.daumcdn.net/cfile/tistory/99251D4B5C7620F616)
> 추상화
> 출처 : https://shinsunyoung.tistory.com/18
- 객체의 공통적인 특징(기능, 속성)을 도출
- 객체지향적 관점에서 클래스의 정의 또한 추상화라고 할 수 있다.

#### Java에서의 추상화
1. 추상 클래스 : abstract
	- 부모로서의 사용은 가능하지만, **객체로서의 사용은 불가능**하다.
2.  추상 메소드 : 본체가 없는 메소드
- 추상 클래스를 상속받은 후 재정의하여 사용
```Java
abstract class Animal{ // 추상클래스
	public abstract void eat(); //추상 메소드
	public abstract void sleep(); //추상 메소드
	public int bite(){ // 메소드
		System.out.println("물었다!");
		return  0;
	}
} 
class Dog extends Animal{ // A를 상속받은 B
	@Override
	public void eat(){ 
		System.out.println("개가 먹는다");
	}
	@Override
	public void sleep(){
		System.out.println("개가 잔다");
	}
} 
public class abstractTest{ 
	public static void main(String[] args) { 
		Dog obj = new Dog(); 
		obj.eat(); // 개가 먹는다 
		obj.sleep(); // 개가 잔다 
		obj.bite(); // 물었다!  
		// Animal obj2 = new Animal(); // error 
	} 
}
```
3. 인터페이스 : interface
- 추상 메소드만을 가질 수 있다.
- 상속 받는 클래스에서는 인터페이스의 모든 메소드를 구현해야 한다.
- 동일한 동작을 약속하기 위해 사용된다.
- extends 대신 implements를 통해 인터페이스를 상속받는다.

##### 추상 클래스와 vs 인터페이스
-   메소드의 유형
    -   추상 클래스 : 추상 메소드(선택) + 일반 메소드
    -   인터페이스 : All 추상 메소드
-   변수의 final의 여부
    -   추상 클래스 : X
    -   인터페이스 : 기본적으로 final을 붙임
-   클래스인가?
    -   추상 클래스 : O
    -   인터페이스 : X
-   목적
    -   추상 클래스 : 상속 받아 기능을 확장해나감
    -   인터페이스 : 구현 객체의 같은 동작 보장
-   다중 상속
    -   추상 클래스 : 불가능
    -   인터페이스 : 가능

### 4. 다형성(Polymorphism)
- 동일한 이름의 함수를 약간 다른 방법으로 동작하게 만드는 방법
- ex) 오버라이딩, 오버로딩
	- 오버라이딩(Overriding) : 부모클래스의 메소드와 같은 이름을 사용하고, 매개변수도 같지만, 내부 소스를 재정의한다.
	- 오버로딩(Overloading) : 같은 이름의 함수를 여러 개 정의한 후 매개변수를 다르게 하여 같은 이름을 경우에 따라 호출하여 사용하는 것

## 객체 지향 설계 5원칙(SOLID)
로버트 마틴이 정한 2000년대 초반 5가지 기본 원칙.
### S : 단일 책임 원칙(Single Responsibility Principle)
 한 클래스는 하나의 책임만 가져야 한다.
### O : 개방-폐쇄 원칙 ( Open/closed Principle)
소프트웨어 요소는 확장에는 열려있으나 변경에는 닫혀 있어야 한다.
### L : 리스코프 치환 원칙(Liskov Substitution Principle)
프로그램의 객체는 프로그램의 정확성을 깨뜨리지 않으면서 하위 타입의 인스턴스로 바꿀 수 있어야 한다.
### I : 인터페이스 분리 원칙 (Interface Segregation Principle)
특정 클라이언트를 위한 인터페이스 여러 개가 범용 인터페이스 하나보다 낫다.
### D : 의존관계 역전 원칙(Dependency Inversion Principle)
프로그래머는 추상화에 의존해야, 구체화에 의존하면 안된다.

## 객체 지향 프로그래밍의 장점

### 소프트웨어의 생산성 향상
객체지향 프로그래밍은 소프트웨어의 재사용을 지향한다. 
- 코드를 재사용하기 쉽다(상속, 캡슐화, 다형성)
- 업그레이드가 쉽다.
- 디버깅이 쉽다.

### 실세계에 대한 쉬운 모델링
- 응용 소프트웨어를 하나의 절차로 모델링하기 어렵다.(많은 물체들의 상호 작용으로 묘사하는 것이 더 쉽고 적합)
- 실세계에 대한 모델링을 좀 더 쉽게 해준다.(모든 것을 객체들의 상호작용으로 생각)
### 보안성 향상
- 캡슐화의 특징으로, 실제로 구현되는 부분을 외부에 드러나지 않도록 하여 정보를 은닉한다.

## 객체지향 프로그래밍의 단점
### 느린 실행 속도
- 캡슐화와 격리구조 때문에 절차지향 프로그래밍보다 실행 속도가 느리다.
- 추가적인 메모리와 연산에 대한 비용이 추가 된다.






출처
http://www.incodom.kr/%EA%B0%9D%EC%B2%B4_%EC%A7%80%ED%96%A5
https://radait.tistory.com/5
https://chanhuiseok.github.io/posts/java-1/
https://jeong-pro.tistory.com/95
