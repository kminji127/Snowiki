---
description: 자바란 무엇인가
---

# Chapter 1

### 1.0. Java의 이름의 유래

* Sun MicroSystems의 제작자인 James Gosling, Arthur Van, Andy Bechtolsheim에서 유래&#x20;
* 1991년 가전제품(Consumer Electronics)에 도입했으나 실패&#x20;
* 1992년 “Oak”라는 인터프리터 개발&#x20;
* 1993년 TV에 도입했으나 실패&#x20;
* 1994년 웹 브라우저에 도입하여 성공&#x20;
* 1995년 SunWorld’95에서 Java가 각광받게 됨 현재까지 거의 모든 기업들이 Java를 사용하고 있음

### 1.1. 자바의 환경

![](<../../.gitbook/assets/image (5).png>)

**자바 개발 환경 (Java Development Kit, JDK)**&#x20;

* 개발자가 자바 기반 애플리케이션 개발을 위해 다운로드하는 소프트웨어 패키지&#x20;
* JRE + 개발을 위해 필요한 도구(javac, java등) + 컴파일러와 클래스 라이브러리 등을 포함하고 있음

**자바 실행 환경(Java Runtime Environment, JRE)**&#x20;

* 자바 프로그램을 실행하기 위한 소프트웨어&#x20;
* JVM이 자바 프로그램을 동작시킬 때 필요한 라이브러리 파일들(JVM + Java 클래스들)을 가지고 있음

**자바 가상 머신(Java Virtual Machine, JVM)**&#x20;

* 자바 소스코드로부터 만들어진 자바 바이너리 파일(.class)을 실행함&#x20;
* 자바 실행 환경(JRE)에 의해 생성&#x20;
* 애플리케이션을 제어할 수 있는 실행 유닛&#x20;
* PC에서부터 다양한 디지털 기기에 활용됨 (하드웨어를 제어하는 운영체제와 유사한 역할. 자바를 위한 특별한 운영체제)&#x20;
* 자바의 변형 버전으로는 안드로이드가 있음

**Java의 특징**

![](https://lh6.googleusercontent.com/DT4aI8j4La-M63undkNx-ilXXpiG4sBeqrArvN7QQThMKEuyZS5yfr5m7hyvwn-565Oe2pNNLCCXmf-g0xg\_zCwLbzoABgG7-iW6JXqkPU75Fy3aIcXJiXDgB9p\_bwMrg5NT0h40)

* 클래스(Class): 소프트웨어 공학 관점에서 매우 중요한 개념&#x20;
* JVM: 디지털 기기에 꼭 필요한 운영체제(OS)와 유사 CBD(Component Based Design/Development): 비즈니스 모델을 만들 때 유용함 → 기업에서 자바가 많이 쓰이는 이유&#x20;
  * 여기서 Component = Class&#x20;
* OOP(Object Oriented Programming): 객체지향 프로그래밍 언어&#x20;
* GUI: 사용자가 그래픽을 통해 컴퓨터와 정보를 교환하는 환경&#x20;
* Applet: 보안 문제



### 1.2. 자바 타입&#x20;

* J2SE: PC에서 돌아가는 버전. 일반적인 사용자들이 많이 쓰는 버전&#x20;
* J2EE: 서버에서 돌아가는 버전. 기업용&#x20;
* J2ME: 모바일용. 지금은 사용되지 않고 안드로이드로 넘어감

### 1.3. 자바 플랫폼 (Virtual Machine)&#x20;

* J2SE: JVM&#x20;
* J2EE: HotSpot&#x20;
* J2ME: CVM, KBM, CardVM

자바 실행 환경(JRE): 자바 가상 머신(JVM) + 자바 기본 라이브러리(클래스 등)&#x20;

* 하드웨어 → OS → Adapter → JVM → 자바 기본 클래스 → 자바 기본 API → 자바 애플리케이션 클래스 파일(.java)&#x20;
* Java Runtime Execution(Engine) = Java Virtual Machine

![](https://lh6.googleusercontent.com/qhgAQ54-V-5K2JuGriobQa0WyVWDbjnv1HfsqKKAu2wIerhEnhX-KDb81N8VpCTOgsZ0YTJLUtZ7Gyewlj-CM5C69r7QscyUbYg8gfEuX\_vUQmkhJ2-u5Ptpc1EeKGAUjUXRxDqF)

### 1.4 자바 프로그램&#x20;

* Java Application (O)&#x20;
* Applet (X)&#x20;
* Midlet (X)&#x20;
* Activity (2-2학기 때 다룰 예정)&#x20;
* Servlet (??)&#x20;
* xlet&#x20;
* JSP (Java Server Page)&#x20;
* Ajax&#x20;
* JavaScript&#x20;
* JSON (JavaScript Object Notation)

타겟 디바이스에 따라 달라지는 자바 프로그램&#x20;

* PC: Class MyClass extends Applet&#x20;
* 모바일 기기: Class MyClass extends Midlet&#x20;
* 서버: Class MyClass extends Servlet&#x20;
* 안드로이드 기기: Class MyClass extends Activity&#x20;
* xxx 기기: Class MyClass extends xxxlet&#x20;

→ let: 실행 Unit 생성됨 → 죽지 않고 계속 실행되고 있도록 만들어짐

### 1.5. 자바 언어의 특징&#x20;

* 객체 지향 프로그래밍 패러다임&#x20;
* RMI, And CORBA, JDBC 등 분산 환경을 지원&#x20;
* 바이트코드&#x20;
  * 컴파일러가 자바 언어를 중간 언어 형태인 바이트코드로 컴파일 → 인터프리터가 해석&#x20;
* architecture-neutral(아키텍처 중립적)&#x20;
  * 동일한 프로그램의 자바 바이트코드는 JVM이 설치된 어떤 플랫폼에서도 실행 가능&#x20;
* Multiple Threads(다중 스레드 지원) → 성능 향상&#x20;
* GUI를 이용한 event handling이 용이



### 자바에서 클래스와 인스턴스, 객체란 무엇인가?&#x20;

* 클래스: 연관되어 있는 변수와 메소드의 집합이다.&#x20;
* 인스턴스: 클래스를 구체적인 실체로 만든 것이다.&#x20;
  * → 클래스가 설계도라면, 인스턴스는 제품이다.&#x20;
* 설계도인 클래스가 구체적인 실체인 인스턴스가 되었을 때 객체라고 부른다.



* System.out.println() : 콘솔 화면에 출력하는 명령어&#x20;
  * System.in : 키보드로 입력받음&#x20;
  * System: 화면. 자바의 기초적인 IO&#x20;
* String: 문자형 타입
* import java.util : 패키지 불러오기. 컬렉션 프레임워크, 일부 국제화 지원. 클래스, 서비스 로더, 속성, 임의 번호 생성, 문자열 구문 분석 및 검색 클래스 등 여러 기타 유틸리티 클래스를 불러올 수 있다.&#x20;
* new: 키워드&#x20;
* Date: 생성자(Constructor). 밀리세컨드의 시간을 제공하는 클래스이다.&#x20;
* 생성자: 인스턴스를 생성해주는 역할을 하는 특수한 메소드. 클래스와 같은 이름을 갖고 있다.&#x20;
* 메소드: 클래스 내의 함수 자바의 함수는 따로 존재하지 않고 클래스 내에 존재한다.



### 1.9. 자바 언어의 특징&#x20;

* 소문자와 대문자를 구별한다.&#x20;
  * 클래스 이름은 반드시 대문자로 시작하며, 명사형으로 한다. (ex. ChattingServer)&#x20;
  * 메소드 이름은 반드시 소문자로 시작하며, 목적어는 대문자로 한다. (ex. getName, setLevel)&#x20;
  * 변수명은 반드시 소문자로 시작하며, 동사형으로 한다.&#x20;
* 디렉토리 내의 파일 이름은 한글 대신 영어로 지정하는 것이 좋다.&#x20;
* 환경 변수를 올바르게 설정해야 한다.&#x20;
* applet과는 달리 항상 main 클래스가 존재한다.&#x20;
* 파일 이름은 클래스 이름과 같다. 따라서 파일 이름도 항상 대문자로 시작한다.&#x20;
* 단, 파일 이름은 JDK에 있는 클래스 이름과 같으면 안 된다.

### 1.10. 자바 프로그램의 구조&#x20;

* Package statement: 비슷한 성격의 자바 클래스들을 모아 넣는 자바의 디렉토리&#x20;
* import statements: 다른 패키지나 클래스를 참조&#x20;
  * 패키지를 참조하게 되면 클래스 앞에 public이 붙게 된다. public이 붙은 변수, 메소드는 어떤 클래스에서든 접근 가능하다.&#x20;
  * public 이외의 접근 생성자&#x20;
    * private: 해당 클래스에서만 접근 가능&#x20;
    * default: 해당 패키지 안에서만 접근 가능&#x20;
    * protected: 같은 패키지 안의 클래스, 또는 해당 클래스를 상속 받은 외부 패키지에서 접근 가능&#x20;
* 클래스&#x20;
  * 클래스: 연관되어 있는 변수와 메소드의 집합&#x20;
  * 생성자: 인스턴스를 생성해주는 역할을 하는 특수한 메소드. 클래스와 같은 이름을 갖고 있다.&#x20;
  * 메소드: 클래스 내의 함수. 자바의 함수는 따로 존재하지 않고 클래스 내에 존재한다. 객체지향 프로그래밍의 핵심은 클래스를 만드는 것이다.

**컴파일러와 인터프리터**

* 컴파일러(Compiler): 소스코드를 object code(객체 코드)로 변환하는 프로그램. 컴퓨터가 이해할 수 있는 기계어로 변환한다.&#x20;
* 링커(Linker): 오브젝트 코드를 합쳐 하나의 실행 파일(.exe)로 만든다.&#x20;
* 인터프리터(Interpreter): 고급 언어로 작성된 원시코드 명령어들을 한 줄씩 읽어들여 실행하는 프로그램. 고급 명령어를 중간 형태로 번역한 다음에 실행한다.

![](https://lh3.googleusercontent.com/K0tDuRB\_6DjOKPv\_7mZdR194RtEMUB12b6qh9DIVohT4JDLDTynz7vcXU-bdyEn3upmcbAy8DDhUR5\_6ZcGK9M9CRN3n1euSWTU6CD7w0CskrVap3ERzIxCc7ZV10Ddujo2NNRDy)

(사진 출처: https://lucete1230-cyberpolice.tistory.com/157)

→ 자바는 컴파일러와 인터프리터의 결합 형태를 지닌다.&#x20;

* 자바 프로그램(.java) → Javac(컴파일러) → 바이트 코드(.class) → Java(인터프리터)&#x20;
* → Java Virtual Machine이 한 줄씩 해석하여 실행 (시작 → 명령어 얻음 → 명령어 실행)&#x20;
* 바이트 코드 = Java Virtual Machine이 해석할 수 있는 언어&#x20;
* Java Virtual Machine: JVM이란? : 자바 소스코드로(.java)부터 만들어진 자바 바이너리 파일(.class)을 실행하며, 자바 실행 환경(JRE)에 의해 생성된다. PC에서부터 다양한 디지털 기기에 활용되며, 하드웨어를 제어하는 운영체제와 유사하다. 즉, 자바를 위한 특별한 운영체제이다.

**프로그램 언어 동작 방식**

* Compile-Behavior 방식&#x20;
  * 컴파일을 할 때 필요한 변수와 공간을 확보하는 방식&#x20;
  * malloc(): 일종의 동적 메모리 할당 → C언어
* Run-time Behavior 방식&#x20;
  * 실제로 실행되면서 필요한 변수와 공간을 확보하는 방식&#x20;
  * 동적 메모리 할당&#x20;
  * 객체지향 프로그래밍은 이 방식을 따른다.
