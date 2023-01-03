# Variable

## 시작하기
```dart
void main() {
  print('Hello world!');
}
```

## 변수(Variable)
```dart
var name = 'Dart';
print(name); // Dart
name = 'Flutter';
print('Hello ${name}'); // Hello Dart
```
- 같은 scope 안에서 변수 재선언 불가

### 변수 타입
```dart
// 정수
int num1 = 10;
int num2 = -15;

// 실수
double num3 = 2.5;
double num4 = 0.5;

// Boolean
bool isTrue = true;
bool isFalse = false;

// 문자
String name1 = 'Flutter';
String name2 = 'Dart';
print(name1 + ' ' + name2);
print('I love ${name1}');
print('I love $name2');

// dynamic
dynamic name = 'Google';
name = 4;
print(name);
```
- var: 타입을 보고 유추하는 동적 타입, 중간에 타입 변경 불가
- dynamic: 동적 타입, 중간에 다른 타입으로 변경 가능

**null값 가능 여부**
- nullable
- non-nullable
```dart
// non-nullable
String name = 'black';
name = null; // error

// nullable
String? name2 = null;
print(name2);

String? name3 = 'pink';
print(name3!); // 현재 not null
```

**final과 const**
- 공통점: 변수 재할당 불가, 타입명 생략 가능
- 차이점: const는 빌드 타임의 값(작성하는 순간의 값)을 알아야 함
  - DateTime.now() 등 실시간으로 할당되는 변수의 경우 const 오류 발생
```dart
final String name = 'dart';
name = 'flutter'; // error

const String name2 = 'dart';
name2 = 'flutter'; // error

const name3 = 13; // int

final DateTime now = DateTime.now();
const DateTime now = DateTime.now(); // error
```