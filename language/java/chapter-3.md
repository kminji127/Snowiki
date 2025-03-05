---
description: 객체지향
---

# Chapter 3

### 3.1. 객체 지향 프로그래밍의 기본 원리

* 프로그램은 객체라는 소프트웨어 컴포넌트(software component)로 만들어진다.&#x20;
* Software Component: 다시 사용할 수 있는 범용성을 위해 개발된 소프트웨어 구성 요소&#x20;
* CBD(Component Based Development): 컴포넌트 기반 개발 방법론. 여러 시스템이나 소프트웨어에서 재사용할 수 있도록 컴포넌트를 만들고 재조립하는 개발 방법론.&#x20;
  * 각 기능 별로 분리하여 개발하고, 이를 재사용함으로써 소프트웨어 개발에 드는 반복적인 작업과 시간 절약&#x20;
* 객체는 데이터와 메소드를 포함하여 서비스(service) = 기능, 행위, 할 일(function)을 제공 → Component == Class == Object&#x20;
* 객체 지향 프로그래밍은 설계한 객체 인스턴스(object instance)를 기반으로 실행됨&#x20;
* **객체 인스턴스(object instance)**: 데이터와 메소드가 포함된 (정의되고) 구현된 실체화&#x20;
  * 실체화 = 메모리 heap 영역에 필요한 공간이 만들어짐&#x20;
  * class를 사용하여 객체를 정의 (Define) ← .java 파일&#x20;
  * new를 사용하여 객체 인스턴스를 구현(Create) ← 실행 결과&#x20;
* 클래스(Class)&#x20;
  * 실제 세계의 컨셉을 추상화하고 표현한 것
  * 클래스 객체는 개발자/프로그래머에 의해 프로그램에 정의됨
  * 객체 (인스턴스)는 프로그램이 실행될 때 동적으로 생성됨 (new를 사용함으로써)
  * 같은 클래스 안에 여러 개의 객체 (인스턴스)가 생성될 수 있음
* **객체(Object)**: 메모리 공간(heap 영역)에 생성된 인스턴스

![](https://lh5.googleusercontent.com/Ofnqovs96Mva9hhBwneHOIaMW84iWQGwBBP6Q6VuNgFffELUtUOPI5tt5pxRd6Z3XkfHgzTxKW2jpp0IqGUUZ\_w0re0LaZdQWllgcTMl00Fww9NxrPTAWiXCmzDFwAgHdtNRzfK8)

* OOP의 단계&#x20;
  * 실제 세계를 추상화(abstraction)
  * 클래스를 정의
  * 클래스 객체 인스턴스 생성 - 생성 시점을 잘 고려해야 함
  * 클래스 객체 실행 - 프로그램 로직에 따라
* **컴포넌트(Component)**
  * 서비스를 위한 메소드(기능)를 가진 일종의 클래스
  * HIPO의 기본 컨셉
    * HIPO (Hierarchy Input Process Output): Input-Process-Output으로 이루어진 모듈을 계층적으로 나타낸 도표
    * 시스템의 분석 및 설계나 문서화에 사용 되는 기법으로 계층을 구성하는 각 모듈별 실행 과정인 입력, 처리, 출력 기능을 나타냄
    * 소프트웨어 공학의 기본 구조
    * input을 output으로 변형하는 일종의 프로그램 요소
* Java는 CBD 디자인을 기본적으로 갖고 있으며, 다른 언어보다도 클래스라는 개념을 잘 표현하고 있음
* 컴포넌트가 모여 하나의 큰 소프트웨어 모델이 됨



### 3.2. Class

소프트웨어 컴포넌트의 기본&#x20;

클래스를 어떻게 만드는지가 객체지향의 핵심&#x20;

* 사물(Object): 생각이나 실제 세계에 존재하는 존재 또는 개념 - 인스턴스 이전의 객체&#x20;
* **추상화(Abstraction)**: 사물의 공통적인 특징(common characteristics)을 추출하는 과정&#x20;
* 클래스(Class): 사물의 공통점을 모은 것
* 공통점 중에서 value들은 필드(Field)로 표현 → Member Field&#x20;
* 공통 특징의 함수는 메소드(Method)로 표현 → Method(Member Function) = service&#x20;
* **캡슐화(encapsulation)**: 클래스의 공통점 외부로부터의 접근 방지
* 정보 숨기기(Information Hiding): 클래스 외부로부터 접근 방지&#x20;
* **상속(Inheritance)**: 존재하는 클래스의 속성을 포함시키는 것

![](https://lh4.googleusercontent.com/-dbyqQ9r6sFeyZxNOlD2ocpTdOu69FnbEMHxTV2CFhrHC6jn6IK9XJS4mcmeKAK6gYCUII7re5w8E7-4LuQRmnySdFrkyZzOZ6ZMBxaX26V4Nn45VOkjpG6ZGf-II23ThR2GRCKt)

* 모든 사물을 추상화 → 클래스 정의 (Fields, Methods) → 자동으로 캡슐화 및 Information Hiding&#x20;
* 필요할 때는 다른 클래스에 있는 메소드를 상속(Inheritance)하기도 함

#### 추상화 (Abstraction)

* 타겟 시스템의 객체, 사물, 컨셉 선택하기 (목적 확인)&#x20;
  * 고려할 대상 선정 → 추상화의 대상(객체, 개체)&#x20;
  * ex) 음식점 솔루션 / 고객, 음식, 재료, 메뉴&#x20;
* 공통점 생각하기&#x20;
  * 대상들 간의 관계 선정 → 추상화의 기능&#x20;
  * 고객 → 주문 → 음식 | 재료 |
* 추상화
  * 공통점으로부터 액션과 속성을 추출하고 묘사하기&#x20;
* 추상화한 후 일반화&#x20;
  * 동일한 객체: 실제 세계의 사물의 일반화&#x20;
  * 동일한 행위: 적용할 함수의 일반화&#x20;
  * 동일한 속성: 사용할 데이터의 일반화

#### 모델링 (Modeling)&#x20;

* 속성과 데이터를 일반화
* 클래스 정의

#### 클래스 인스턴스(Class Instance)

* 객체, 사물의 추상화 ← 개념 설계 단계&#x20;
  * 추상적인 Object = 데이터 + 메소드&#x20;
* Class ← 정의 단계&#x20;
  * Class = Object을 잘 기술한 것&#x20;
* Object (Class Instance) ← 실행 단계&#x20;
  * (Class Instance) Object = 클래스의 인스턴스&#x20;
* 객체 지향 프로그램 프로그램 = 클래스의 서로 다른 메소드를 호출하는 (Class Instance) Object의 집합

메소드 호출(Method Invocation)

* 객체에 대한 함수를 호출
* 다른 클래스에 있는 메소드를 호출
* Run-Time Executive(JRE)라 부르는 Virtual Machine에서 실행해줌
* Signature = Message = 함수의 이름, 변수의 수, 변수의 타입&#x20;
* 메시지 패싱(Message Passing)을 기반으로 함: 클래스 내부에 선언된 변수는 클래스 내부의 메소드로만 핸들링&#x20;
* 다른 클래스에 있는 메소드를 컨트롤&#x20;
* ECA Rule을 기반으로 함&#x20;

![](https://lh4.googleusercontent.com/jw4coBoOkrDB28GPKSZ7SvnfO4QeacS2Q4s7uCL4NyUCbFD1Z3GmH0IN1-dDZcgFe-VTknKdHWjDyir2-wUJmVib7csDMkuNe0xTKLrDCELgVP7OjJaqDqZiMgjp0gw6Tlxj6ELC)

* Pedal 클래스: push() 함수&#x20;
* Engine 클래스: powerUp() 함수&#x20;
* Wheel 클래스: speedUp() 함수&#x20;
* Car 클래스: engine, pedal, wheel 객체 생성 / 다른 클래스에 있는 함수 호출 (method invocation)&#x20;
* Driver 클래스: 메인 클래스 / car 객체 생성 / car의 pedal.push() 함수 호출

#### 자바 클래스

![](https://lh5.googleusercontent.com/zC41-\_SEDuyHI-XeAZCPrWpCM0q7ujdx1lTSprq5SSj69y-qcGa0xv5mfTKiNAzE\_Z0JL-0Pqv\_cTj1gAp3h31X8NjFmtyjh1iD3Zpk2mWKOH7MxtvrW4Jv8sg\_qxQQfno2-P0Xc)

![](https://lh5.googleusercontent.com/7DGgMHLAGNuOSr7lNVShPf76owqiFHUxQzBr\_eaVCwfASWEF-7q\_jWwLVG4DqD-C5045iXrFRvpuqHitfrG3LmUM7Fw3ODiI74mikgKTly-DbBG8XRyv2sl9hwdC0xIELgxCMag4)

**제어자(modifier)**: 클래스, 변수 또는 메소드의 선언부에 함께 사용되어 부가적인 의미를 부여&#x20;

어디까지 공개할 것인지 결정 (Visibility and Accessibility)&#x20;

* 클래스 제어자: public, abstract, final&#x20;
  * public: 다른 클래스에서 접근 가능&#x20;
  * abstract: 추상, 미완성 - 선언부만 작성하고 실제 수행 내용은 구현되지 않은 상태&#x20;
  * final: 변경할 수 없는 값이나 상속 또는 재정의를 허용하지 않을 때&#x20;
* 접근 제어자(Access Modifier)
  * public: 어디서든 접근 가능(클래스 내부, 같은 패키지, 다른 패키지 모두 허용)
  * protected: 같은 패키지 안의 클래스, 또는 해당 클래스를 상속 받은 클래스에서만 접근 가능
  * default(기본값): 같은 패키지 내에서만 접근 가능
  * private: 해당 클래스에서만 접근 가능

  | 접근 제어자 | 동일 클래스 | 동일 패키지 | 자식 클래스 | 전체(외부 클래스) |
  |-----------|---|---|---|---|
  | public    | O | O | O | O |
  | protected | O | O | O | X |
  | default   | O | O | X | X |
  | private   | O | X | X | X |
* 변수 제어자: static (한 번 생기면 상속되더라도 바뀌지 않음)

주요 키워드&#x20;

* import: 외부에서 만들어진 패키지와 클래스를 사용할 때 사용하는 키워드&#x20;
* class: 연관된 변수와 메소드의 집합. 가장 기본이자 핵심 키워드&#x20;
* interface: 클래스가 구현해야 하는 동작을 선언하는 데 사용되는 추상 자료형&#x20;
* extends: 단일 상속 (기본). 상속 받는 대상이 클래스&#x20;
* implements: 다중 상속. interface로 만들어진 클래스를 상속 받음&#x20;
* new: 객체를 만드는 키워드&#x20;
* super: 부모 지칭&#x20;
* this: 현 객체(자기 자신) 지칭

#### 생성자 (Constructor)

* 클래스와 이름이 같은 함수
* 돌려주는 return 값이 없음&#x20;
* 멤버 필드를 초기화(initialization)하는 역할을 함 → 똑같은 이름이라도 초기화를 다르게 할 수 있음 → 다르게 수행됨&#x20;
* 기본 생성자가 존재 (권장하지 않음)

#### 오버로딩(Overloading)&#x20;

* 이름은 같지만 데이터 타입이 다른 메소드 → Signature&#x20;
* ex) 먹는 방식은 한국인, 미국인, 일본인 각각 다르다&#x20;
* 이름은 같지만 기능, 수행될 내용은 다름&#x20;
* ad-hoc polymorphism이다 = 어떤 argument가 적용되느냐에 따라서 다르게 행동하는 함수
* 함수의 Signature = 함수 이름 + 인자(argument) 수 + 인자 타입&#x20;
  * ECA rule의 Condition Check가 이를 체크하는 역할을 함

#### 오버라이딩(Overriding)

* 존재하는 함수를 재정의
* 용도: 실행할 코드를 구현하는 경우 인터페이스에 있는 메소드는 이름만 있고, 실제 코드는 없음&#x20;
* 상속을 받았을 때, 부모 클래스를 재정의&#x20;
* static이면 상속되더라도 바뀌지 않으므로 오버라이딩이 안 됨

![](https://lh3.googleusercontent.com/Dw7lOHqr\_nhwRz\_SQy57nUrigFf7ylIbj7OVlodunRjeRBDvkSA81tvfJSxOIKrtReXviVYS-jzC9YkUEjzX9CLbP-lDBBgnYVOZjUyCAgrHoa0tsueiXttAv4P-FDWDP\_tRo5zh)

#### 패키지(Package)

* 주어진 특정 서비스를 위한 클래스의 집합&#x20;
* 각 클래스의 첫 번째 줄에 패키지 이름을 묘사 (package _Package\_name_)&#x20;
* 패키지 사용법 import _Package\_name_.Class\_name;

#### this, super&#x20;

* this: 현 객체(자기 자신) 지칭 - heap 영역을 가리키는 참조 포인터&#x20;
* super: 부모 지칭&#x20;
* this(): 자기 자신을 초기화하는 함수. 멤버 필드를 다시 초기화하는데 사용됨&#x20;
* super(): 부모 클래스 생성자를 불러오는데 사용됨&#x20;
* instanceof: 객체의 클래스 타입을 체크&#x20;
  * 사용 사례) 어떤 클래스의 인스턴스였는지 체크

### 3.3. 상속(Inheritance)&#x20;

* 존재하는 다른 속성을 확장하고 싶을 때 상속함&#x20;
* Is-a Relationship&#x20;
  * 의미/분류/속성의 계층적 개념&#x20;
  * 예) 인간 → 여성 → 여자 대학생 → 공대 여자 대학생&#x20;
  * 개념들이 계층화됨

Java에서의 상속&#x20;

* 단일 상속: 하나의 클래스를 상속 - extends 키워드&#x20;
* 다중 상속: 여러 인터페이스를 상속 - implements 키워드&#x20;
* 오버라이딩 복습: 상속받을 때 인터페이스의 메소드를 재정의



### 3.4. super, super()&#x20;

* super&#x20;
  * super(부모) 클래스에 접근하는 레퍼런스&#x20;
  * 부모 클래스의 필드나 메소드를 참조할 때 사용되는 키워드&#x20;
  * ex) super.attribute / super.method()&#x20;
* super()&#x20;
  * super(부모) 클래스의 생성자(constructor)를 호출하는 함수&#x20;
  * 상속받은 부모의 속성을 가져와서 만든다&#x20;
  * 생성자의 시작 부분에 사용된다



### 3.5: Interface&#x20;

* 클래스가 구현해야 하는 동작을 선언하는 데 사용되는 추상 자료형
* 자바에서 자주 사용되는 함수(메소드)를 정의하는 개념&#x20;
* 함수명과 변수만 정의되고 실제 실행 코드는 없음&#x20;
* 상수(final), 구현부 없는 추상 메소드만 선언할 수 있음 (+ Java 8부터는 static, default 메소드도 선언 가능)
* 실행 코드의 정의는 사용될 때 구현됨&#x20;
* 인터페이스 클래스를 구현하는 클래스는 implements 키워드를 사용&#x20;
* ex) class My\_Class implements Interface Student&#x20;
* JAVA RMI에서의 IDL 사용을 참조&#x20;
* 주로 AWT와 SWING에서의 이벤트 처리에서 사용됨
* **IDL**(Interface Definition Language): 인터페이스를 묘사하기 위한 명세 언어&#x20;
  * 원격 메소드 호출(Remote Method Invocation: RMI)을 할 때, 데이터베이스, 애플리케이션, 클라이언트가 구현한 객체들 간의 메시지 전송을 할 때 사용된다.&#x20;
  * n개의 모듈들이 같은 이름을 사용해야 할 경우, 미리 이름만 정의하는 것이다.&#x20;
  * 미리 common 함수들을 정의하는 것이다.&#x20;
  * 어느 한 언어에 국한되지 않는 언어중립적인 방법이다.&#x20;
  * 인터페이스를 표현함으로써, 같은 언어를 사용하지 않는 소프트웨어 컴포넌트 사이의 통신을 가능하게 한다.
* **jar (Java Archive)**: 소프트웨어에서 수많은 자바 클래스 파일과 연관 메타데이터, 리소스(텍스트, 그림 등)을 하나의 파일로 모아서 자바 플랫폼에 응용 소프트웨어나 라이브러리를 배포하기 위한 패키지 파일 포맷


#### 💡`TIL`💡 인터페이스 타입으로 변수를 선언하고 구현체로 객체를 생성하는 이유
```java
// 예시
List<Integer> numbers = new ArrayList<>();
```
> 결론: 구현체와의 결합도를 낮추고 코드의 유연성을 높임 → 객체 지향 설계 원칙을 따륾

- 예시 코드의 특징
    - ArrayList가 List 인터페이스를 구현(implements)하고 있음
    - ArrayList는 List가 정의한 모든 메서드를 구현해야 하며, ArrayList 객체는 List 타입으로 선언 가능
    - List는 더 상위 개념이기 때문에 코드의 수정 없이도 LinkedList, Vector 등 다른 리스트 구현체로 쉽게 변경 가능
- 장점
    1. **유연성**
        - 다른 구현체로 쉽게 변경 가능
          - 예) ArrayList 대신 LinkedList로 변경하고 싶다면 `numbers = new LinkedList<>(numbers);` 코드로 변경 가능
    2. **코드의 재사용성**
        - 다양한 구현체에서 동일한 인터페이스 메서드를 사용할 수 있음
            - 예) List 인터페이스: 객체가 순서대로 저장되며, 인덱스를 사용해 요소에 접근할 수 있는 자료구조
            - 주요 메서드: add(), get(), remove(), size() 등 (어떤 종류의 리스트에서도 동일한 메서드 이름으로 사용 가능)
    3. **인터페이스 기반 프로그래밍**
        - Java에서는 **구현체가 아닌 인터페이스에 의존**하도록 하는 것을 권장
        - 객체의 실제 구현과 관계없이 일관된 방식으로 데이터를 처리할 수 있으며, 프로그램이 **구현체의 세부 사항에 종속되지 않도록** 함
    

### 3.6: static과 final&#x20;

### static
* static 멤버 필드(변수)&#x20;
  * 객체 간 전역 변수(global variable)처럼 사용됨&#x20;
  * 클래스 이름에 의해 접근 (ex. Color.red)&#x20;
  * 한 번 생기면 상속되더라도 바뀌지 않음&#x20;
* static 메소드 (class method)&#x20;
  * 클래스명으로 메소드를 호출 (클래스 인스턴스 아님!)&#x20;
  * 객체를 생성하지 않고도 바로 사용 가능&#x20;
  * this, super을 사용하지 않음&#x20;

#### 💡`TIL`💡 변수 선언 시 static 여부에 따른 차이
- 해당 변수가 있는 클래스 로드 중에 초기화
    - 반면, non-static(static 키워드 없이 생성된) 변수는 새로운 객체를 생성할 때마다 초기화됨
- 애플리케이션 실행 내내 메모리에 머물러 있음
    - jvm의 static 메모리(해당 영역은 프로그램이 시작하고 종료될 때까지 살아있음)
- ⇒ 따라서 초기화 과정 없이 해당 변수, 메소드에 접근 가능
- 클래스의 모든 인스턴스에 대해 동일
- 클래스의 모든 인스턴스가 액세스 가능


### final
* final 클래스 = 상속 불가&#x20;
  * 해당 클래스를 상속할 수 없음 = 서브 클래스를 만들 수 없음
  * heap 영역에 공간이 만들어지지 않으므로 상속하면 컴파일 에러 발생&#x20;
  * `참고` 불변 객체(immutable object)는 final로 선언되어 있어 서브 클래스를 통한 변경 불가
* final 멤버 필드(변수) = 변경 불가&#x20;
  * 값을 바꿀 수 없는 상수처럼 사용됨&#x20;
  * 값을 초기화할 수만 있고, 새로운 값을 할당할 수는 없음&#x20;
  * 한 번 초기화되면 값을 변경할 수 없음 (참조 변수에 저장된 주소 변경 불가)
  * 인스턴스 변수로 사용 시, 생성자에서 값을 할당하고 그 이후에는 값을 변경할 수 없음
  * 참조 자체를 변경할 수 없게 하지만, **참조된 객체의 내부 상태는 변경 가능**
    - 참조된 객체의 주소값은 고정되기 때문
    - ex) ArrayList 내부의 요소들은 변경이 가능 = 즉, 외부에서 직접 접근할 수는 없으나, 만약 외부에 numbers를 노출하거나, 내부에서 변경하는 메서드를 제공한다면 리스트의 요소를 추가하거나 삭제하는 작업은 가능
* final 메소드 = 재정의 불가&#x20;
  * 오버라이딩이 불가한 메소드&#x20;
  * 서브 클래스에서 메서드를 재정의(Override)할 수 없음

#### 💡`TIL`💡 final의 목적
- 초기 설정(초기화한 값)을 변경하지 않도록 하기 위해
- 즉, final로 인스턴스 변수나 클래스 변수를 선언하는 동시에 초기화 작업이 필요함

#### 💡`TIL`💡 왜 final 변수는 생성과 동시에 초기화를 해야 할까?
- 생성자나 메소드를 통해 초기화 작업을 하면 변수의 중복이 발생할 가능성이 있다. 이것은 final로 변수를 선언하는 기본적인 이유인 초기 설정을 변경 없이 유지하는 것에 위배된다.
- 매개 변수나 지역 변수를 final로 선언하는 경우 초기화 작업 없이 사용 가능
    - 매개 변수는 이미 초기화가 되어서 넘어 왔고, 지역 변수는 메소드를 선언하는 중괄호 내에서만 참조되므로 다른 곳에서 변경할 일이 없다.
    - 하지만 final로 선언된 변수이기 때문에 초기에 할당된 값을 변경하려고 하면 에러 발생

#### 💡`TIL`💡 불변 객체(immutable object)
- 객체가 생성된 후 상태가 변경되지 않는 객체
- 변경이 필요할 경우 새 인스턴스를 생성함
- 동시성 문제를 방지하고, 예상치 못한 부작용을 줄이는 데 유리
- 불변 객체인 것
    - String
    - Java의 기본 자료형(primitive types)을 객체로 감싸는 **래퍼 클래스**(Integer, Long, Double, Boolean 등)
    - java.time 패키지의 날짜 및 시간 클래스 (LocalDate, LocalTime, LocalDateTime, ZonedDateTime, Instant 등)
    - java.util.Collections.unmodifiable*()로 만든 컬렉션
    - Enum
    - final 클래스로 선언하고, 모든 필드를 final로 설정한 경우

### 3.7: 내부 클래스(Inner Class)&#x20;

* 정의
  * 클래스 안에 만들어진 클래스&#x20;
  * Nested Class라고 불림&#x20;
  * 외부 클래스의 멤버 필드와 메소드에 접근할 수 있음&#x20;
* 종류&#x20;
  * Member Class&#x20;
    * 클래스처럼 정의&#x20;
    * .java 안에서만 사용&#x20;
    * 반복적인 기능을 사용하고 싶을 때 사용&#x20;
  * Local Class: 메소드 안에 이름과 함께 선언&#x20;
  * Non-named Class: 메소드 안에 선언 (이름 없음)&#x20;
  * Inner Class를 사용하는 이유? 이벤트 처리(event handling)를 지원하기 때문에&#x20;
  *   Event Handling Methods&#x20;

      1\) Listener을 상속, 이벤트를 처리하기 위해 클래스 안에 action을 구현

      2\) 이름 있는 inner class로 event handler 생성&#x20;

      3\) 이름 없는 inner class로 이벤트 처리

      4\) event handling을 independent class로써 구현

      5\) event handling을 lambda 표현을 사용하여 구현

      → 자세한 내용은 7.2 Event Programming에서!



### 3.8: Java에서의 중요한 클래스&#x20;

* Object 클래스: 모든 클래스의 조상&#x20;
* 데이터 타입 클래스: Boolean, Byte, Short, Integer(int는 그냥 타입), Double, Long, Float&#x20;
* Math 클래스: 수학에서 자주 사용하는 상수들과 함수들을 미리 구현해 놓은 클래스&#x20;
* String 클래스: 문자열을 위한 클래스&#x20;
* StringTokenizer 클래스: 문자열을 개별 토큰으로 분리하는 클래스&#x20;
* Vector 클래스: 데이터를 가변 크기로 설정할 수 있고, 요소의 개수에 따라 자동으로 크기 조절을 하는 클래스

#### 💡`TIL`💡 래퍼 클래스 (Wrapper Class)
- Java의 기본 자료형(primitive types)을 객체로 감싸는 래퍼 클래스
- 래퍼 클래스가 필요한 이유
    1. 컬렉션 프레임워크 사용
        - Java의 컬렉션 프레임워크(List, Set, Map)는 객체만 저장할 수 있음
        - 기본 자료형은 저장할 수 없기 때문에, 기본 자료형을 래퍼 클래스로 감싸야만 컬렉션에 저장 가능
        - 예: List<Integer> numbers = new ArrayList<>();
    2. 제네릭과의 호환성
        - Java의 제네릭은 객체에 대해서만 사용 가능
        - 기본 자료형을 사용하는 경우, 제네릭을 사용할 수 없어 래퍼 클래스로 변환하여 객체로 다루어야 함
        - 예: Optional<Double> value = Optional.of(3.14);
    3. 기능 제공
        - 각 래퍼 클래스는 유용한 상수와 메서드를 제공
        - Integer 클래스는 parseInt(), MAX_VALUE와 같은 유틸리티 메서드와 상수를 제공하여 기본 자료형을 더 쉽게 처리 가능
        - 예: int max = Integer.MAX_VALUE;
    4. 값의 표현과 변환 용이
        - 문자열 변환 및 파싱 기능을 제공하여, 기본 자료형 값을 문자열로 변환하거나 문자열을 해당 기본 자료형으로 변환 가능
        - 예: int number = Integer.parseInt("123");
    5. null 표현 가능
        - 기본 자료형은 null을 가질 수 없지만, 래퍼 클래스는 객체이므로 null을 할당할 수 있음
        - 데이터베이스의 결과값이나 외부 시스템 통신 시, 값이 없는 상황을 처리할 때 유용
        - 예: Integer age = null;
    6. 자동 박싱과 언박싱
        - 자동 박싱(autoboxing)과 언박싱(unboxing)을 통해 기본 자료형과 래퍼 클래스 간의 변환을 자동으로 수행
        - 기본 자료형을 객체처럼 사용할 수 있으며, 필요한 경우 JVM이 자동으로 변환을 수행
        - 예: List<Integer> list = new ArrayList<>(); list.add(5); // int 5가 Integer로 자동 박싱됨

![](https://file.notion.so/f/f/a1d13819-2c56-4071-8fab-ae53c8fff718/b5af74f4-c229-45a6-84da-4cf2bf2c701c/image.png?table=block&id=13ece954-7edc-805d-afc5-cdb305e9b56d&spaceId=a1d13819-2c56-4071-8fab-ae53c8fff718&expirationTimestamp=1740873600000&signature=NbuACdwsrNh58M02lMOKn5qbK--Oqvz6XoF3HuIN1PI&downloadName=image.png)


### 3.9: 예외 처리 (Exception Handling in Java)&#x20;

* 간단한 에러(예외)가 발생하면 종료되지 않고 계속 실행될 수 있도록 예외 처리&#x20;
* Java에서는 탄력 있는(resilient) 코드를 짤 수 있도록 예외(exception)를 사용 (try-catch)&#x20;
* C언어에서의 예외 처리&#x20;
  * signal 함수(시스템 호출) 또는 함수의 return value 체크 → 음수나 0이면 오류&#x20;
  * 함수를 실행할 때 return value를 체크하여 비정상적인 상황을 처리&#x20;
* Java에서 제공하는 예외 클래스 예시&#x20;
  * ArithmethicException: 0으로 나눴을 때&#x20;
  * ArrayIndexOutofBoundsException: 배열의 크기보다 큰 원소를 접근
  * NegativeArraySizeException: 배열의 크기가 음수&#x20;
  * NullPointerException: 생성되지 않은 객체를 이용해서 객체 멤버에 접근&#x20;
* 키워드&#x20;
  * throws: 발생할 예외 선언&#x20;
    * Java에서 제공할 수도 있고 개발자가 정의할 수도 있음&#x20;
    * public int doSomething(int x) <mark style="color:blue;">throws</mark> Exception1, Exception2&#x20;
  * throw: 예외 클래스 object를 생성&#x20;
    * <mark style="color:blue;">throw</mark> new Exception1();&#x20;
  * try-catch-finally&#x20;
    * try: 발생할 예외&#x20;
    * catch: 예외 처리 (여러 개 있을 수 있음)&#x20;
    * finally: 예외와 상관없이 실행되는 부분(선택)&#x20;
* 예외 처리 절차&#x20;
  * 예외 클래스 정의 `Class MyTypeException extends Exception { .. }`
    * 일반 예외(컴파일러가 체크): Exception 상속&#x20;
    * 실행 예외(컴파일러가 체크하지 않음): RuntimeException&#x20;
  * throws를 사용하여 함수에서 발생할 예외 선언 `method_name() throws MyTypeException { .. }`
  * 예외가 발생하는 조건에서 throw를 사용하여 예외 클래스를 생성 `throw new MyTypeException();`
  * 위의 예외가 발생할 부분에 try-catch를 선언하여 실행 `try { .. } catch (MytypeException) { .. }`

### 3.10: Generics in Java&#x20;

* 자바 1.5버전부터 컴파일 타입 체크를 제공하기 위해 추가된 개념&#x20;
* Generic: 데이터 타입을 일반화(generalize). 클래스나 메소드에서 사용할 내부 데이터 타입을 미리 지정하는 방법&#x20;
* collection class에서 형 변환을 할 때 발생할 오류 방지&#x20;
* 많은 자료구조들이 collection class라고 선언되어 있음&#x20;
* 구조를 일반화시킴으로써 collection class을 안전하게 사용&#x20;
* Generics을 사용하는 이유&#x20;
  * 클래스와 인터페이스를 정의할 때 타입을 매개변수(parameter)처럼 전달되도록&#x20;
  * type parameter는 같은 코드를 다른 input으로 재사용하는 방법을 제공함&#x20;
  * parameter를 어떤 타입으로 할 것인가를 미리 설정&#x20;
  * 장점 컴파일할 때 강력한 타입 체크 → 자료형을 선언할 필요가 없어짐

### 3.11: Collection Types in Java&#x20;

Collection: 다양한 element를 하나의 유닛으로 묶는 객체 (다른 객체를 저장, 핸들링하는 것을 목적으로 하는 객체)&#x20;

* 자료를 저장, 회수, 다룰 때 유용함&#x20;
* 다른 메소드로 데이터를 전송하기 유용함&#x20;
* 프로그램 = 자료구조 + 알고리즘 (Logic + Procedure)&#x20;
* 자료구조의 예시: Stack, Queue, List, Array, Map, Table 등

#### Collection Framework&#x20;

* 다수의 데이터를 쉽고 효과적으로 처리할 수 있는 표준화된 방법을 제공하는 클래스의 집합&#x20;
* 데이터를 저장하는 자료구조와 데이터를 처리하는 알고리즘을 구조화하여 클래스로 구현해 놓은 것

포함하는 것

* Interfaces&#x20;
* Implementations ( → 개발자 구현)&#x20;
* 알고리즘 (for each Collection class: Methods)

Generic Type의 매개 변수

* \<E> : element
* \<K> : key
* \<V> : value
* \<N> : number
* \<T> : type

![](https://lh6.googleusercontent.com/N-sffXmpEClVdReY17NjGn9XT2FkwSJ5\_HUyPHO3EDAPL7UhQb-Pg7Z2Tt31FGGSa\_BimGECh3FhhJUyWhDEWRlgHyiu8hMeH4UrPtRd2bgtO4sIg-b19AWDQfvmEx9aYs2CAo-T)![](https://lh4.googleusercontent.com/qUf4IpmaWsuh0eJw9fbw\_fJEKSKSXuO\_C5sCOhLLe49LFxahKpBqe7juBVpVv9MsUewe0Y8t7y2YHgHIu1vp5NeaGY42ONbaa54WAHyXqzXUTA\_FWOxlPORSUCJo0I3mOqkWTADX)

#### Interface List&#x20;

* ArrayList&#x20;
  * 배열을 이용하기 때문에 인덱스를 이용해 배열 요소에 빠르게 접근 가능&#x20;
  * 저장된 요소는 순차적으로 저장됨&#x20;
  * 랜덤 접근이 용이함&#x20;
  * 삽입 및 삭제하기 어려움&#x20;
  * 필요하면 사이즈를 재조정&#x20;
* LinkedList&#x20;
  * 연결 리스트를 이용하여 요소 저장&#x20;
  * 저장된 요소는 비순차적으로 분포되며, 링크(link)로 연결되어 구성됨&#x20;
  * 삽입 및 삭제가 용이함&#x20;
  * 랜덤 접근하기 어려움

#### Interface Set&#x20;

* HashSet&#x20;
  * 요소를 순서에 상관없이 저장하고 중복된 값은 저장하지 않음&#x20;
  * 요소를 빠르게 찾고 추가 가능&#x20;
* TreeSet&#x20;
  * 데이터가 정렬된 상태로 저장되는 이진 검색 트리(binary search tree)의 형태로 요소를 저장&#x20;
  * 데이터를 추가, 제거하는 동작 시간이 빠름&#x20;
  * 요소를 순서에 상관없이 저장하고 중복된 값은 저장하지 않음

#### Interface Map&#x20;

* HashMap: 순서가 없다 빠르다&#x20;
* TreeMap: 순서가 있다

