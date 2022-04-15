---
description: Java AWT
---

# Chapter 4

### 4.1 AWT(Abstract Window Toolkit)

* GUI (Graphical User Interface)를 제공하는 함수들의 집합
* AWT 관련 패키지: java.awt
  * GUI 컴포넌트를 위한 클래스가 들어있는 패키지
* **Swing**: AWT를 확장한 GUI 프로그래밍 도구
  * AWT보다 더 많은 종류의 GUI 컴포넌트 제공
  * Swing 관련 패키지: javax.swing
* 안드로이드 GUI와 유사

**AWT의 기본 구조**

* java.lang.Object (모든 자바 클래스의 조상 클래스)
  * BorderLayout: 경계면 기준 (Center, East, West, South, North)
  * CardLayout: 여러 개의 카드를 쌓아 보여줌
  * FlowLayout: 화면 크기에 맞추어 순서대로 정렬하여 배치
  * GridLayout: 행과 열을 미리 정의

\=> 틀을 나타내는 Layout 클래스들은 Object 클래스를 상속받음

* Component
* MenuComponent

\=> GUI의 핵심 구성 요소

**각 컴포넌트의 계층 관계**

![](<../../.gitbook/assets/0 (6)>)

![](<../../.gitbook/assets/1 (4)>)

**Component 클래스**

* AWT GUI 컴포넌트들의 최상위 클래스 → AWT GUI 컴포넌트들은 Component 클래스의 속성을 모두 갖고 있음 (java.awt.Component)
* AWT 컴포넌트에서 자주 사용되는 메소드를 갖고 있음
* 주요 메소드
  * add(PopupMenu): 추가
  * getSize(): 컴포넌트의 사이즈 반환
  * setBackground(Color): 배경색 설정
  * setEnabled(boolean): 컴포넌트 활성화 여부 설정
  * setFont(Font): 글꼴 적용
  * setForeground(Color): 전경색 설정
  * setLocation(int, int): 위치 설정
  * **setSize(int, int): 사이즈 설정**
  * **setVisible(Boolean): 프레임 시각화**

**Container**

* 다른 컴포넌트를 포함할 수 있는 컴포넌트
* add() 메소드를 사용하여 다른 컴포넌트를 추가
* 컨테이너에 담기는 컴포넌트는 컨테이너의 설정을 따름(변경 가능)
* **Panel**
  * 빈 평면 공간만 가진 종속적 컨테이너
  * 눈에 보이지 않지만 컴포넌트들을 모아줄 때 사용
  * Panel 안에 Panel 삽입 가능
  * 컴포넌트의 다양한 배치에 유용

### 4.2 AWT의 주요 컴포넌트

**1) Frame**

* Java의 기본 GUI 컴포넌트
* title과 레이아웃을 가진 Windows 컨테이너
* 생성자:
  * Frame()
  * Frame(String title): 프레임 제목
  * ex) Frame f = new Frame("OOP"); // OOP 프레임 생성
* setSize(int width, int height): 사이즈 설정 (픽셀 단위)
* setVisible(true): 프레임 시각화 여부
* setTitle(String): 프레임 제목
* setLayout(new 레이아웃명()): 레이아웃 설정 (default: BorderLayout)
* **프레임 참조변수.add(컴포넌트 참조변수): 컨테이너에 컴포넌트 추가**

**2) Label**

* static text의 한 줄을 표시하는 컴포넌트
* 생성자:
  * Label()
  * Label(String text) // 텍스트
  * Label(String text, int alignment) // 텍스트, 정렬방식
    * alignment는 LEFT(0), CENTER(1), RIGHT(2) 중 선택
  * ex) Label lb = new Label(“Java”);
* getAlignment(): 정렬 반환
* getText(): 텍스트 반환
* setAlignment(int alignment): 정렬 설정
* setText(String text): 텍스트 설정

\* Frame이 들어갈 클래스와 Main 클래스를 분리하는 것을 권장!

**3) Button**

* 사용자가 마우스로 클릭했을 때 액션이 수행되도록 하는 컴포넌트
* 버튼을 누르면 자동으로 Method Invocation(메소드 호출)
* ECA(Event Condition Action) Rule
* Event: 함수 호출 - \[이벤트 발생]
* Condition: 어떤 함수를 호출했는가 확인 - \[이벤트에 해당하는 조건 확인]
  * 메시지 내용, Signature 체크
  * 메시지 패싱 = Signature를 전달
* Action: 함수를 실행
* 메소드 호출 → Signature(Message) 생성 → 메시지 패싱 → Condition 체크 → 메소드 실행
* 생성자:
  * Button() // 텍스트가 없는 버튼
  * Button(String label) // 텍스트가 있는 버튼
* addActionListener(): Event 실행 시켜주기 위한 설정
  * 클릭 → ECA → action 메소드 실행
* getLabel(): 버튼의 문자열 텍스트 반환
* setLabel(): 버튼의 문자열 텍스트 설정
* getActionCommand(): 버튼에 의해 발생한 액션 이벤트의 명령 이름 반환
* setActionCommand(): 버튼에 의해 발생한 액션 이벤트의 명령 이름 설정

![](<../../.gitbook/assets/5 (6)>)&#x20;

**4) Checkbox and CheckboxGroup(Radio Button)**

* 선택 여부를 표현하는 컴포넌트
* checkbox를 통해 체크박스와 radio 버튼 생성 → 다중 선택 가능
* 생성자:
  * Checkbox()
  * Checkbox(String text)
  * Checkbox(boolean state)
  * Checkbox(String text, boolean state) // 텍스트, 체크 여부
* **Checkboxgroup**은 그룹 내 체크박스 중 하나만 선택 가능
  * 생성자: Checkboxgroup(String text, CheckboxGroup group, boolean state) //생성자에서 그룹명 추가됨
* addItemListener() → Event 관련
* getState(), setState(Boolean): 선택 상태 반환
* getLabel(), setLabel(String): 문자열 텍스트 반환
* getSelectedCheckbox(): 선택된 체크박스 반환

![](<../../.gitbook/assets/10 (2)>)

**5) Choice**

* 여러 아이템 중 하나를 선택할 수 있게 만든 컴포넌트
* 생성자: Choice()
* addItemListener() → Event 관련
* add(String item): 목록에 아이템 추가
* remove(int position), remove(String item): 아이템 지우기
* getItem(int), getItemCount(), getSelectedIndex(), getSelectedItem(): 아이템/개수/선택된 인덱스/선택된 아이템 반환
* select(int position), select(String item): 위치/아이템 선택

![](<../../.gitbook/assets/12 (3)>)

**6) List**

* 여러 아이템 중 여러 개를 선택할 수 있게 만든 컴포넌트
* 생성자:
  * List()
  * List(int rows) // 줄 수
  * List(int rows, boolean) // 줄 수, 다중선택 가능 여부
* addActionListener() → Event 관련
* addItemListener() → Event 관련
* add(String item): 목록에 아이템 추가
* removeAll(), remove(int position), remove(String item): 아이템 삭제
* getItem(int), getItemCount(), getSelectedIndex(), getSelectedItem()
* select(int position), select(String item): 위치/아이템 선택

![](../../.gitbook/assets/13)![](<../../.gitbook/assets/14 (3)>)

**7) Text Components**

* 공통 메소드
  * setEditable(Boolean): 수정 가능 여부
  * setText(String): 텍스트 설정
  * getSelectedText(), getText(): 선택한 텍스트 반환
* **TextField**
  * 사용자로부터 데이터를 입력받을 수 있는 컴포넌트
  * 한 줄만 입력 가능
  * 생성자:
    * TextField()
    * TextField(String text) // 텍스트
    * TextField(int columns) // 열 수
    * TextField(String text, int columns) // 텍스트, 열 수
  * AddActionListener() → Event 관련
  * setEchoChar(char): 비밀번호 (char을 미리 설정하면 어떤 걸 입력해도 해당 char으로 표시됨)
* **TextArea**
  * 여러 줄의 텍스트를 입력할 수 있는 컴포넌트
  * 생성자:
    * TextArea()
    * TextArea(String text)
    * TextArea(int rows, int columns)
    * TextArea(String text, int rows, int columns) // 보여질 텍스트, 행, 열
  * AddActionListener() → Event 관련
  * append(String): 현재 열에 추가
  * insert(String, int position): 지정된 열에 추가
  * replaceRange(String, int start, int end): 다른 텍스트로 대체
  * select(int start, int end): 특정 텍스트 선택
  * selectAll(): 텍스트 전체 선택

![](<../../.gitbook/assets/15 (2)>)

**8) Panel**

* 빈 평면 공간만 가진 종속적 컨테이너
* 눈에 보이지 않지만 컴포넌트들을 모아줄 때 사용
* Panel 안에 Panel을 삽입 가능
* 컴포넌트의 다양한 배치에 유용
* 생성자:
  * Panel()
  * Panel(LayoutManager layout) // 레이아웃
* add(component): 다른 컴포넌트 추가
* setSize(), setLocation()

![](../../.gitbook/assets/1)

**9) ScrollPane**

* 화면이 작아지면 스크롤 바를 제공하는 컨테이너
* 제한된 공간에서 큰 컴포넌트를 보여줄 때 사용
* 단 하나의 컴포넌트만 포함 가능
* 여러 개의 컴포넌트를 포함하려면 ScrollPane 안에 패널 넣기
* 생성자:
  * ScrollPane()
  * ScrollPane(int scrollbarDisplayPolicy) // 스크롤바 표시 여부

![](<../../.gitbook/assets/3 (2)>)

**10) PopupMenu**

* 마우스를 클릭했을 때 메뉴를 보여주는 컨테이너
* event 처리: ActionListener 클래스 포함
* 생성자:
  * PopupMenu()
  * PopupMenu(String label)
* add(), show(), hide()

![](<../../.gitbook/assets/4 (4)>)

### 4.3 Layout

* default layout
  * BorderLayout: Window, Frame, Dialog
  * FlowLayout: Panel

**1) FlowLayout**

* 화면 크기에 맞추어 왼쪽부터 오른쪽으로 순서대로 정렬하여 배치
* 정렬: CENTER(기본), RIGHT, LEFT
* 생성자:
  * setLayout(new FlowLayout())
  * setLayout(new FlowLayout(Flowlayout.Right, 10, 20)) // 정렬, 좌우 간격, 상하 간격

![](../../.gitbook/assets/5) ![](<../../.gitbook/assets/6 (3)>)

**2) BorderLayout**

* 경계면을 기준으로 중앙, 동, 서, 남, 북으로 분할 (Center, East, West, South, North)
* 생성자:
  * setLayout(new BorderLayout())
  * setLayout(new BorderLayout(10, 20)) // 좌우 간격, 상하 간격
* 예시:
  * add("North", new Button("North"))
  * add(panel, BorderLayout._SOUTH_);

![](<../../.gitbook/assets/7 (4)>) ![](<../../.gitbook/assets/8 (2)>)

**3) GridLayout**

* 행과 열을 미리 정의 - \[행:열]
* 내용과 관계 없이 격자 간격은 똑같음
* 왼쪽에서 오른쪽, 위에서 아래 순서대로 배치
* 생성자:
  * setLayout(new GridLayout(r, c)) // 행, 열
  * setLayout(new GridLayout(3, 2, 16, 39)) // 행, 열, 좌우 간격, 상하 간격

![](<../../.gitbook/assets/15 (3)>)

**4) CardLayout**

* 여러 개의 카드를 쌓아 보여주듯 컴포넌트를 포개어 배치
* 생성자: CardLayout card = new CardLayout()
* 레이아웃 설정: setLayout(card)
* 추가: add("First", 컨테이너) // 순서 설정
* 출력: show(부모 컨테이너, String name)
* 마우스 관련 event: addMouseListener()

**5) GridBagLayout**

* GridLayout을 기반으로 하는 복잡한 레이아웃
* 하나의 컴포넌트를 2개 이상의 셀로 확장
* 셀의 크기를 정할 수 있음
* 필드
  * int gridX : 컴포넌트가 놓인 열의 위치
  * int girdY : 컴포넌트가 놓인 행의 위치
  * int gridwidth : 컴포넌트가 차지하는 가로 넓이
  * int gridheight : 컴포넌트가 차지하는 세로 넓이
  * fill : 컴포넌트 확대하는 방법. 가로, 세로 가로-세로 채우기(BOTH) 방법이 있다.
  * double weightX : 가로 방향 여유 공간 채우는 방법
  * double weightY : 세로 방향 여유 공간 채우는 방법
* 사용 순서
  * 생성자: GridBagLayout gridbag = new GridBagLayout()
  * 크기 생성자: GridBagConstraint constraint = new GridBagConstraint()
  * 프레임 레이아웃 설정: setLayout(gridbag)
  * 크기 설정: constraint.weightx / gridheight / gridwidth
  * gridbag.setConstraints(컴포넌트, constraint)
  * add(cell) → 컨테이너에 컴포넌트 추가

![](../../.gitbook/assets/18)

**4.4 Menu**

* pull-down과 popup 메뉴로 구분 (여기서는 pull-down menu를 다룸)

1. MenuBar 생성
2. Menu 오브젝트 생성
3. 각 Menu 아래에 하위 MenuItem 생성

**4.5 Dialog**

* 팝업 윈도우의 형태로, 특정 설정을 하거나 사용자에게 정보를 보여주는 용도
* pack() : 사이즈를 알아서 딱 맞추어서 설정해줌
* 생성자: Dialog(Dialog owner, String title, boolean) // Dialog 객체의 소유자, 제목, 모달 여부
* modal 속성: 해당 Dialog가 작업 종료를 하지 않으면 다른 곳의 작업을 할 수 없음
* 프레임과 별도로 공개 여부를 설정 (setVisible)

**4.6 FileDialog**

* 파일을 선택해서 여는 기능을 제공
* 생성자:
  * FileDialog(Frame)
  * FileDialog(Frame, String) // 소속될 프레임, 제목
