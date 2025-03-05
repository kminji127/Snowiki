---
description: Java 언어
---

# Chapter 2

### 2.1. 자바 구별자(Identifier)&#x20;

* 클래스 이름, 메소드 이름, 변수 이름&#x20;
* 문자와 숫자의 연속&#x20;
* 항상 문자로 시작한다 (숫자나 \_ $ 이외의 기호로 시작할 수 없음)&#x20;
* true, false, null, try과 같은 키워드는 사용할 수 없다.
* \_나 $로 시작할 수 있다.&#x20;
* 대문자와 소문자를 구별한다.&#x20;
* 길이 제한이 없다.&#x20;
* 띄어쓰기 불가



### 2.2. 자바 키워드&#x20;

<mark style="color:red;">객체지향에서 중요한 키워드</mark>

* package: 비슷한 성격의 자바 클래스들이 모인 한 덩어리&#x20;
* class: 연관된 변수와 메소드의 집합. 가장 기본이자 핵심 키워드&#x20;
* interface: class와 같은 개념&#x20;
* extends: 단일 상속 (기본). 상속 받는 대상이 클래스&#x20;
* implements: 다중 상속. interface로 만들어진 클래스를 상속 받음&#x20;
* import: 외부에서 만들어진 패키지와 클래스를 사용할 때 사용하는 키워드&#x20;
* private: 해당 클래스에서만 접근 가능&#x20;
* protected: 같은 패키지 안의 클래스, 또는 해당 클래스를 상속 받은 외부 패키지에서 접근 가능&#x20;
* public: public이 붙은 변수, 메소드는 어떤 클래스에서든 접근 가능&#x20;
* new: 객체를 만드는 키워드&#x20;
* super: 부모 지칭&#x20;
* this: 현 객체(자기 자신) 지칭&#x20;
* static: \[상속 관련] 한 번 생기면 상속되더라도 바뀌지 않음&#x20;
* final: \[상속 관련] 함수나 클래스를 상속시키지 않을 때 사용하는 키워드

![](https://lh4.googleusercontent.com/0zDa-OcRs0bj5DhGpX8budnl4aP1eG3lnL1RhSDau5dtaYNRUh-kkm\_5ucDT4m6us3x8BfBwuYhsLFKlsvbjyuoNMhoNQOxD92w6A8jMk00fH\_GUK0i6jOgkaHSWlvxTzcWg\_OFK)

<mark style="color:blue;">예외처리 키워드</mark>&#x20;

* try: 예약어. 에러를 감지하는 역할&#x20;
* catch: 에러를 예외 처리&#x20;
* finally: 에러 발생 여부와 상관 없이 반드시 실행&#x20;
* throw Exception Type: 예외 정의&#x20;
* throws: 예외 발생

<mark style="color:green;">자바 만의 특수 키워드</mark>: native, synchronized, transient, volatile



### 2.3. Java에서의 데이터 타입

* **기본 타입(Primitive Type)**: 실제 값을 변수에 저장 <mark style="background-color:orange;">**(Stack 영역에 생성)**</mark>
  * boolean: 논리형 (true / false)&#x20;
  * char: 16비트 유니코드 문자형&#x20;
  * 정수형&#x20;
    * byte: 8비트 정수(-128 ~ 127)&#x20;
    * short: 16비트 정수(-32,768 ~ 32,767)&#x20;
    * int: 32비트 정수(-2^31 ~ 2^31-1)&#x20;
    * long: 64비트 정수(-2^64 ~ 2^64-1)&#x20;
  * 부동 소수점형(실수)&#x20;
    * float: 32비트 실수&#x20;
    * double: 64비트 실수
* **참조 타입(Reference Type)**: 객체의 번지를 참조하는 타입 <mark style="background-color:orange;">**(Heap 영역에 생성)**</mark>
  * 클래스(Class): 연관되어 있는 변수와 메소드의 집합&#x20;
  * 인터페이스(Interface): 클래스가 구현해야 하는 동작을 선언하는 데 사용되는 추상 자료형&#x20;
  * Array(Matrix): 배열

#### 💡`TIL`💡 변수 타입에 따른 기본값
자바에서 선언되었지만 초기화되지 않은 필드는 컴파일러에 의해 적절한 기본값으로 설정된다. (지역 변수 제외)

|데이터 타입|기본값|
|--|--|
|byte, short, int|0|
|long|0L|
|float|0.0f|
|double|0.0d|
|char|'\u0000'|
|boolean|false|
|참조 타입|null|

### 2.4. 참조 타입 (Reference Type)

* 객체 지향의 핵심&#x20;
* 참조(Reference): 힙(Heap) 영역에서의 동적인 메모리 할당 (dynamic memory allocation) → new라는 명령어를 통해!&#x20;
* **힙 영역(Heap Area)**: 메인 메모리 중에서도 동적으로 생성/소멸되는 메모리를 관리하는 영역&#x20;
  * 모든 자바 클래스의 객체와 배열이 할당되는 곳&#x20;
  * Java Virtual Machine(JVM)이 시작될 때 생성되어 애플리케이션이 실행되는 동안 크기가 유동적으로 변화&#x20;
  * 힙(Heap): 크기 순서대로 정렬하는 알고리즘&#x20;
    * 메모리 덩어리를 크기 별로 정렬하므로 메모리 관리에 활용됨&#x20;
  * 하드 디스크: 프로그램 실행 시 메인 메모리로에 올려놓음&#x20;
  * CPU: 프로그램 수행 시 메인 메모리에 접근&#x20;
  * 메인 메모리: CPU가 사용할 명령어와 데이터가 저장되어 있음. 필요한 공간을 확보
* OOP 실행상의 핵심: 클래스에 대한 **인스턴스**(클래스의 실체화)의 생성&#x20;
* 인스턴스를 Object → Class Instance Object(클래스에 대한 인스턴스 실체) ← Object라고 지칭함 Object-Oriented 실행 → 클래스 내에서 정의된 메소드의 실행 (변수(member field)를 참고) 메소드와 변수를 지칭하는 공간이 힙 영역!

1. MyClass라는 클래스 정의
   1. 변수: name(문자형), type(정수형)
   2. 메소드: action()
2. new 키워드를 통해 클래스 인스턴스 생성
   1. 인스턴스가 됨 = 메모리 공간을 확보하여 할당받음 = 실체화
3. Heap Area에 MyClass 클래스가 저장됨
4. action 메소드는 메인 메모리 내의 Code Segment에 저장됨

![](https://lh3.googleusercontent.com/qMW5tEv9JEKZXl5dgon4luJmVdVhX22tCrZGKjbrzT96QecXhxWnNIT7tCRX2hFw7zLKIjWN8WvXh52H8Of1IJ7shShPT70GECVZQbQghmW-diBO2m2VULtMUjSH-wUCVlTFeqs\_)

* **세그먼트(Segment)**: 메모리의 덩어리. Code, Data, Heap, Stack으로 나뉘며, 각각을 Segment라 부른다.
  * Code Segment: 작성한 코드가 들어가는 부분. Java로 짜여진 프로그램은 컴퓨터가 이해할 수 있는 기계어의 형태로 컴파일 되어 파일 등에 저장되는데, 실제 이 파일의 프로그램에 대한 전체적인 코드 자체가 올라가는 영역
  * Data Segment: 전역(global) 변수, 정적(static) 변수가 저장됨
  * Heap Segment: 동적 할당 데이터가 저장되는 영역., 모든 자바 클래스의 객체와 배열이 저장된다.
  * Stack Segment: 함수 내에 정의된 지역 변수가 저장되는 영역. 지역 변수, 매개변수, 복귀 번지 등 임시적으로 사용되는 데이터를 저장하는 영역 함수를 호출하면 생성되고, 함수가 종료되면 반환된다. Last-in First-Out → 가장 최근에 들어온 데이터가 가장 먼저 나감 → 함수 관리 용이 ※ Heap 영역이 커지면 Stack 영역이 작아지고, Stack 영역이 커지면 Heap 영역이 작아짐

<img src="https://lh5.googleusercontent.com/_vbL1N8Ypy_PzMCOpEWb307sAVmfYaTa_tr8zwRwjnkAoFGwc80MSKyYAMtTiitr-j26tJ904bVmmh9XYShh1lEpk1gMVBGeiiirL6JKWydAtNGA6KY-xqz8dc_lkeGTGFvFV5HK" alt="" data-size="original">

### 2.5. Array(배열)

배열이 Stack Segment와 Heap Area에 할당되는 과정

![](https://lh3.googleusercontent.com/SRMv1cWCUAC7egGat\_XQZLhOaboxbNvIQl1\_Z24E1Ane9IdMv\_zUfDjpBBjdHUQHuDbX7Yl9tkTAcy47zqamyX9GX7DKZo-JLfKf\_IUrsjhZy9Cd2O15cCQTPLR1TTyOj9r9l\_Fl)

### 2.6. 제어 구조(Control Structure)

* args\[]: program argument
  * main 함수를 호출할 때 전달하는 String 타입의 배열 형태
  * cmd 창에 입력하면 공백을 기준으로 배열에 담겨 인자 값(argument)으로 전달된다.
  * 예) args = { "snow" , "flake" }라면, args\[0] = “snow”, args\[1] = “flake”
* if문: args의 길이가 1 이상이면 args\[1]을 출력



### 2.7. 메소드 호출 (Method Calling)

* 메소드(Method): 클래스 안의 함수&#x20;
  * Code Segment에 저장되어 있음&#x20;
  * Object Instance(객체 인스턴스)에 의해 호출됨&#x20;
  * new로 Object Instance 생성 → my.action으로 호출&#x20;
* **메소드 호출(Method Invocation)**
  * 객체 안에 있는 메소드를 실행&#x20;
  * 원격 메소드 호출(Remote Method Invocation: RMI)
    * 분산되어 존재하는 객체 간의 메소드를 원격으로 호출
    * 데이터베이스, 애플리케이션, 클라이언트가 구현한 객체들 간의 메시지 전송
    * JVM에서 언제든 활용할 수 있음
  * **ECA(Event Condition Action)** 규칙에 기반
    * 이벤트 기반 아키텍처 및 액티브 데이터베이스 시스템에서 액티브 규칙을 참조하기 위한 규칙
    * 프로그램이 실행되는데 가장 중요한 원리
    * JVM에서 my.action()을 연동시키는 기능들
      * Event: 함수 호출
      * Condition: 어떤 함수를 호출했는가 확인
      * Action: 코드 수행

![](https://lh5.googleusercontent.com/IxFbRXeR1T1OJ\_yL6csTkCnZz7uqaCYKV2jR7gyfQ7OjlKIp5uJ-QXFr8TTHgkgNf6YlrZJp5ViP04dl3SLabYWcZc3bmtswaEjZTtH6WMt-nJMa2FfcspcnOIq7MUGMy2d4\_x6W)

* Event가 발생하면 Signature가 발생 → Condition으로 전달 → 메소드 실행&#x20;
* 매시지 패싱(Message passing) 기반의 메소드 호출(Method Invocation)&#x20;
* 메시지 패싱(Message Passing): 클래스 내부에 선언된 변수는 클래스 내부의 메소드로만 핸들링&#x20;
* 오버라이딩: 부모와 같은 메소드 사용



![](https://lh3.googleusercontent.com/tmriO67w6\_zId0ZFuG-nlfEKpf30Kj1tMN-\_2g0k2X06s2PGTJe0byLEF2TEiLUQ3AkqvEjRwyYYm9lEiGwTuvb5ivDwCPLq96h3JFOud8F6\_ZG81VjNSiQlqxNP4WB9WFQkcKv7)

* **Call-by-value**: 함수를 호출할 때 값(value)이 넘어가는 것
  * 기본 타입에서 동작&#x20;
  * 함수 호출 시 메모리 공간 안에 임시 공간(Stack)이 생성됨&#x20;
  * 함수 호출 시 전달되는 변수의 값을 복사하여 함수의 인자(argument)로 전달&#x20;
  * 함수가 끝나면 값이 사라짐
  * 함수 안에서 인자의 값이 바뀌어도, 변수의 값은 변하지 않음

1. 100이라는 값이 Stack에 저장됨&#x20;
2. Called 함수는 100이라는 값에 접근&#x20;
3. 만약, 100이 300으로 바뀐다면, Called 함수는 300이라는 값에 접근&#x20;
4. 리턴될 때 300과 called가 사라짐&#x20;

※ Call-by-value는 stack의 값이 바뀜

* **Call-by-reference**: 함수를 호출할 때 주소 값이 넘어가는 것&#x20;
  * 참조 타입(reference type)에서 동작&#x20;
  * heap 영역에 클래스가 저장되며, 함수 호출 시 메모리 공간 안에 임시 공간(Stack)이 생성
  * 함수 호출 시 변수의 주소를 인자(argument)로 전달
  * 함수가 끝나도 값이 남아있음
  * 함수 안에서 인자의 값이 바뀌면, 변수의 값도 함께 바뀜

1. new를 통해 class object 생성: member field → 변수
2. Heap Area에 클래스 공간이 만들어짐
3. Stack에는 100의 레퍼런스 값이 저장됨
4. calling 하면 레퍼런스 값이 따라
5. called 함수(300으로 바꾸는 가상의 함수)가 수행되면 레퍼런스 값을 지칭
6. 100이 300으로 바뀌면 heap area의 값이 바뀜

※ Call-by-reference는 Heap Area의 값이 바뀜



* **활성 레코드(Activation Record)**: 프로그래밍 동작 원리 (Stack 활용)&#x20;
  * 프로시저가 한 번 실행되는데 필요한 정보는 메모리의 연속 블록을 사용하여 관리됨&#x20;
  * 프로시저(procedure)가 호출될 때 활성 레코드가 들어가고, 반환될 때 나간다.&#x20;
  * 반환 값에 대한 공간 : 호출한 프로시저로 결과 값이 전달될 때 사용하며, 반환 값은 효율을 위해 종종 레지스터에 담아 되돌려주기도 함.&#x20;
  * 실 매개변수에 대한 공간 : 호출 시 매개변수가 전달되면 사용&#x20;
  * 제어 링크 : 생략 가능한 공간으로 자신을 호출한 프로시저의 활성 레코드를 가리킴&#x20;
  * 접근 링크 : 생략 가능한 공간으로 다른 활성 레코드에 있는 비지역 자료(nonlocal data)를 참조하는데 사용&#x20;
  * 기계 상태 저장 공간 : 프로시저가 호출되기 바로 전의 기계 상태에 대한 정보를 저장&#x20;
  * 지역 자료에 대한 공간 : 프로시저가 실행될 때 지역적으로 사용되는 자료를 저장&#x20;
  * 임시 변수에 대한 공간 : 식을 계산하는 도중 발생하는 임시 값을 저장

![](https://lh5.googleusercontent.com/bZmaBMI27bjjls6fL4gB4qYV9t-bCB\_OdHpPezwa0jZuygNgw6vdtHsRxQy9i60M5C2ZOiX8SnAgvsWL6\_fVfHGOYXAx5hKEqH2Zc5trsvxRNAKz\_H8jK0bhull4CF6PPV0UjOEN)

