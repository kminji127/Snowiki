---
description: Java Event
---

# Chapter 7

### 7.0 Event Concept

* Event: GUI나 시스템 accident로부터 발생하는 Action
  * Action: 사용자의 버튼 클릭
  * Accident: 시스템의 타임 아웃
* Event-Driven Handling(이벤트 기반 핸들링): 이벤트의 발생에 의해 프로그램의 흐름이 결정되는 방식.&#x20;
  * ECA Rule을 기반으로 함.

![https://lh4.googleusercontent.com/Ztv\_Acb6XhBGQsoGjlRgXraj7NKlrfWKQVxrBlwZvPdA3a02V0UKICP7g96uBrJOmkcVP9EoZSvqNJ2zzm2TzxnBhK3Hy0izHlkg7AZYURHBMG\_V42U1QRyFb0-bdA8U9U6WDQtx](<../../.gitbook/assets/0 (1)>)

**Event Handling with Java**

Event Listener

* Event Object를 다루는 객체
* ECA Rule에서의 Condition Check 역할을 맡고 있음.
* Design 단계: GUI 설계
* 등록: Listener
* Implementation: 구현할 부분

**Event Object in Java Programming**

* 사용자가 GUI에서 Action을 수행했을 때 이벤트 발생
* EventObject 클래스를 상속함
* 이벤트 처리를 위한 메소드를 구현해야 함.
  * e.getSource(): 이벤트를 발생시키는 객체
  * getId(): 이벤트 객체의 타입
  * getActionCommand(): 이벤트 객체를 발생시키는 컴포넌트 이름

**Event Processing Steps in Java**

1. Button 객체 생성
2. Event Listener를 Button 객체에 등록 (addActionListener)

\+ Listener interface를 상속해야 함 (예: implements ActionListener)

1. 버튼 클릭했을 때의 Action 메소드 구현 (actionPerformed)

![](<../../.gitbook/assets/1 (5)>)

![](<../../.gitbook/assets/3 (5)>)

### 7.1 AWT Event Classes

이벤트 컴포넌트의 계층 구조 및 주요 이벤트

* EventObject: Event의 최상위 클래스
* ActionEvent
  * 클릭 버튼 객체
  * TextArea, TextField에서의 ‘text input’
  * 객체 아이템 더블클릭
  * MenuItem 선택 객체
* ItemEvent
  * checkbox, List, ComboBox, Radio 객체를 선택할 때
* MouseEvent, MouseMotionEvent: 마우스 클릭, 마우스 움직임
* KeyEvent: 클릭 키

1\) AWT, Swing Event 종류 및 Listener

![](<../../.gitbook/assets/4 (2)>) ![](<../../.gitbook/assets/5 (1)>)

![](<../../.gitbook/assets/6 (4)>) ![](<../../.gitbook/assets/7 (6)>)

![](<../../.gitbook/assets/8 (6)>) ![](<../../.gitbook/assets/9 (1)>)

### 7.2 Event Programming

어디에, 어떻게 이벤트 핸들링 코드를 구현할 것인가?

1. Inherits Listener: Listener 상속 및 Event Handler Action 정의 (가장 보편적인 방법)

![](<../../.gitbook/assets/10 (5)>)

2\. Named Inner Class (내부적으로 많이 반복할 때)

![](<../../.gitbook/assets/11 (1)>)

3\. No-name Inner Class: 무명의 Inner 클래스 정의 (한 번만 쓸 때)

![](<../../.gitbook/assets/12 (2)>)

4\. Independent Class: 독립 클래스 정의 (다른 사람과 공유할 때)

![](<../../.gitbook/assets/13 (4)>) ![](<../../.gitbook/assets/14 (1)>)

5\. Lambda Expression (간단한 코드)

![](<../../.gitbook/assets/15 (4)>)

### 7.3 Event Types

* Event based on Button : Action Event (사용자가 버튼을 클릭)
* Event based on Text : Text Event, Action Event (사용자가 텍스트 필드 키에서 엔터 키를 누름)
* Event based on Selection with Choice etc : Item Event (사용자가 메뉴 항목을 선택)
* Event based on Keypad : Key Event (사용자가 특정 Key를 사용)
* Event based on Mouse : Mouse Event, MouseMotion Event (사용자가 마우스를 사용)

**1) Button Event Types**

**2) Text Event Types**

**3) Item Event Types**

itemStateChanged (ItemEvent e)

* getItem(): return Selected Object
* getItemSelectable(): return a caused Item
* getStateChange(): return a changed state

**4) Key Event**

* keyTyped(keyEvent e)
* keyPressed(keyEvent e)
* keyReleased(keyEvent e)

**5) Mouse Event**
