---
description: Java 2D and Graphic
---

# Chapter 6

### 6.0 Java 2D and Graphic

* 강력하고 복잡한 자바 2D API 및 Graphics 클래스를 제공
* Graphics 클래스: 그림을 그릴 수 있는 도화지. 기초 도형을 그리는 메소드 제공
* Graphic 클래스의 기본 그룹 2가지

![](<../../.gitbook/assets/0 (3)>)

*
  * Java AWT/Swing: 기본적인 도형, 텍스트, 이미지를 render하기 위해 메소드를 draw, fill하는 메소드
  * Java 2D: 2D 도형 draw, 메소드 설정을 통해 도형 설정

### 6.1 Draw Basic Shape

1. JFrame 생성

![](<../../.gitbook/assets/1 (1)>)

2\. JPanel 생성

![](<../../.gitbook/assets/2 (6)>)

![](<../../.gitbook/assets/3 (6)>)(MyPanel)

3\. Draw 메소드 정의 (draw\_method()를 위한 MyPanel 정의)

* Swing: paintComponent() 메소드
* AWT: paint() 메소드
* Graphics g: 그래픽을 g로 사용한다는 인스턴스화

![](<../../.gitbook/assets/4 (1)>)

4\. 좌표 값 계산

5\. Draw 메소드 호출

![](<../../.gitbook/assets/5 (5)>)

전체 코드:

![](<../../.gitbook/assets/6 (5)>)

⇒ 결과:

![](../../.gitbook/assets/7)

### 6.2 Basic Shape

| **도형 이름**                             | **메소드**                                                                                                 |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| <p>Line</p><p>(직선)</p>                | drawLine()![](<../../.gitbook/assets/8 (1)>) drawPolyline()![](../../.gitbook/assets/9)                 |
| <p>Rectangle</p><p>(사각형)</p>          | drawRect()![](<../../.gitbook/assets/10 (3)>) fillRect()![](<../../.gitbook/assets/11 (5)>) clearRect() |
| <p>3D Rectangle</p><p>(3차원 사각형)</p>   | draw3DRect()![](../../.gitbook/assets/12) fill3DRect()![](<../../.gitbook/assets/13 (2)>)               |
| <p>Round Rectangle</p><p>(둥근 사각형)</p> | drawRoundRect()![](<../../.gitbook/assets/14 (4)>) fillRoundRect()![](../../.gitbook/assets/15)         |
| <p>Oval</p><p>(타원)</p>                | drawOval()![](<../../.gitbook/assets/16 (1)>) fillOval()![](<../../.gitbook/assets/17 (4)>)             |
| <p>Arc</p><p>(호)</p>                  | drawArc()![](<../../.gitbook/assets/18 (2)>) fillArc()![](../../.gitbook/assets/19)                     |
| <p>Polygon</p><p>(다각형)</p>            | drawPolygon()![](<../../.gitbook/assets/20 (1)>) fillPolygon()                                          |

**1) Line**

* **drawLine**(int x1, int y1, int x2, int y2): 좌표 (x1, y1)에서 좌표 (x2, y2)까지의 직선
* **drawPolyline**(x\[] , y\[] , int numPoints): 여러 개의 직선을 이어서 그림

**2) Rectangle**

* **drawRect**(int x, int y, int w, int h): 좌표 (x, y)에서 w x h 크기의 사각형
* **fillRect**(int x, int y, int w, int h): 채워진 사각형
* **draw3DRect**(int x, int y, int w, int h, boolean raised): raised에 따라 볼록하거나(True) 오목한(False) 사각형
* **fill3DRect**(int x, int y, int w, int h, boolean raised): raised에 따라 볼록/오목하게 채워진 사각형
* **drawRoundRect**(int x, int y, int w, int h, int arcWidth, int arcHeight): 좌표 (x, y)에서 w x h 크기의 사각형, 4개의 모서리는 원호로 그림
* **fillRoundRect**(int x, int y, int w, int h, int arcWidth, int arcHeight)

**3) Oval**

* **drawOval**(int x, int y, int width, int height): 좌측 상단 좌표가 (x, y)이고 폭이 width, 높이가 height인 사각형에 내접하는 타원
* **fillOval**(int x, int y, int width, int height): 채워진 타원

**4) Arc**

* **drawArc**(int x, int y, int width, int height, int startAngle, int arcAngle): 좌측 상단 좌표가 (x, y), 폭이 width, 높이가 height인 사각형에 내접하는 타원에서, startAngle을 시작 각도로 arcAngle 각도 만큼의 호
* **fillArc**(int x, int y, int width, int height, int startAngle, int arcAngle): 채워진 호

### 6.3 Color

* java.awt.Color 클래스 사용
* 빛의 3원색 RGB의 성분이 얼마나 함유되어 있는지를 0\~255의 수로 나타냄
* 알파값(색상 투명도)을 가질 수 있음
* 색상 설정 메소드:
  * Color c = Color.red;
  * Color c = new Color(255, 0, 0);
  * Color c = new Color(255, 0, 0, 100); // alpha 값
* 컴포넌트 색상 설정 메소드
  * setBackGround(Color c): 컴포넌트 배경색
  * setColor(Color c): 전경색
  * getColor(): 현재 전경색 반환
* **repaint(): paint 함수를 다시 호출함**

### 6.4 Java 2D

이차원의 그래픽, 텍스트, 이미지를 제공

* 광범위한 그래픽 객체를 그릴 수 있음
* 도형 내부를 gradient나 무늬로 채울 수 있음
* 이미지를 그릴 수 있고 필터링 연산 적용 가능
* 그래픽 객체들의 충돌 감지 메커니즘 제공
* **Rendering Context**
* **setStroke**(Stroke s): 굵기, 스타일
* **setPaint**(Paint paint): 색깔, gradient, 패턴 paint
* **setComposite**(Composite comp): 오버래핑을 기반으로 한 메소드 렌더링
* **setTransform**(Transform x): 이미지 객체의 변형
* **setFont**(Font font)
* **java.awt.geom 패키지**
* line, curve, rectangle, ellipse 등 2D 도형 지원
* 메소드:
  * draw \~\~ 2D()
  * fill \~\~ 2D()
* 단색으로 채우기
  * g2.**setColor**(Color.BLUE);
  * g2.**fill**(ellipse);
* 투명하게 채우기
  * g2.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC\_OVER, 0.50F));
* 그라이언트로 채우기
  * GradientPaint gp = new **GradientPaint**(0, 0, Color.WHITE, 0, 100, Color.RED);
* translate(double x, double y): 위치 변경
* rotate(double theta): 회전
