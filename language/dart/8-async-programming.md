# Async Programming

## Synchronous Programming
```dart
void main() {
  addNumbers(1, 1);
  addNumbers(2, 2);
}

void addNumbers(int num1, int num2) {
  print('계산중: $num1 + $num2');
  print('계산완료: ${num1 + num2}');
}
```
```
계산중: 1 + 1
계산완료: 2
계산중: 2 + 2
계산완료: 4
```

## 핵심 키워드
- `Future`: 미래에서 받아올 값
- `delayed`
  - 1번 파라미터: 지연할 기간
  - 2번 파라미터: 지연 시간이 지난 후 실행할 함수

```dart
void main() {
  Future<String> name = Future.value('코드팩토리');
  Future<int> number = Future.value(1);
  
  addNumbers(1, 1);
  addNumbers(2, 2);
}

void addNumbers(int num1, int num2) {
  print('계산중: $num1 + $num2');
  Future.delayed(Duration(seconds: 2), () {
    print('계산완료: ${num1 + num2}');
  });
  print('함수 완료');
}
```
```
계산중: 1 + 1
함수 완료
계산중: 2 + 2
함수 완료
(2초 뒤)
계산완료: 2
계산완료: 4
```

## async, await
- `await`: 기다리라는 명령어
- 기다리는 순간에도 CPU는 다른 작업을 수행
```dart
void addNumbers(int num1, int num2) async {
  print('계산중: $num1 + $num2');
  
  await Future.delayed(Duration(seconds: 2), () {
    print('계산완료: ${num1 + num2}');
  });
  
  print('함수 완료: $num1 + $num2');
}
```
```
계산중: 1 + 1
계산중: 2 + 2
계산완료: 2
함수 완료: 1 + 1
계산완료: 4
함수 완료: 2 + 2
```

```dart
void main() async {
  final result1 = await addNumbers(1, 1);
  final result2 = await addNumbers(2, 2);
  print('result1: $result1');
  print('result2: $result2');
  print('result1 + result2 = ${result1 + result2}');
}

Future<int> addNumbers(int num1, int num2) async {
  print('계산 시작: $num1 + $num2');
  
  await Future.delayed(Duration(seconds: 2), () {
    print('계산 완료: ${num1 + num2}');
  });
  
  print('함수 완료: $num1 + $num2');
  
  return num1 + num2;
}
```
```
계산 시작: 1 + 1
계산 완료: 2
함수 완료: 1 + 1
계산 시작: 2 + 2
계산 완료: 4
함수 완료: 2 + 2
result1: 2
result2: 4
result1 + result2 = 6
```

## Stream
- `Future`: 앨범에서 이미지 가져오기, 현재 배터리 표시, 파일 가져오기, http 요청 등 일회성 응답에 사용
- `Stream`: 위치 업데이트, 음악 재생, 스톱워치 등 계속해서 데이터의 변화를 감지하고 그에 맞춰 적절한 처리를 할 때 사용
  - `yield`: return과 비슷하게 값을 반환해주는데, 한번에 하나씩 return함과 동시에 함수가 종료되지 않고 계속 열려있으면서 지속적으로 return해줌

```dart
import 'dart:async';

void main() {
  final controller = StreamController();
  final stream = controller.stream.asBroadcastStream();
  
  final streamListener1 = stream.listen((val) {
    print('Listener 1 : $val');
  });
  
  final streamListener2 = stream.listen((val) {
    print('Listener 2 : $val');
  });
  
  controller.sink.add(1);
  controller.sink.add(2);
  controller.sink.add(3);
  controller.sink.add(4);
  controller.sink.add(5);
}
```
```
Listener 1 : 1
Listener 2 : 1
Listener 1 : 2
Listener 2 : 2
Listener 1 : 3
Listener 2 : 3
Listener 1 : 4
Listener 2 : 4
Listener 1 : 5
Listener 2 : 5
```
```dart
import 'dart:async';

void main() {
  calculate(2).listen((val) {
    print('calculate(2): $val');
  });
}

Stream<int> calculate(int number) async* {
  for(int i = 0; i < 5; i++) {
    yield i * number;
    
    await Future.delayed(Duration(seconds: 1));
  }
}
```
```
calculate(2): 0
calculate(2): 2
calculate(2): 4
calculate(2): 6
calculate(2): 8
```

```dart
import 'dart:async';

void main() {
  playAllStream().listen((val) {
    print(val);
  });
}

Stream<int> playAllStream() async* {
  yield* calculate(1);
  yield* calculate(1000);
}

Stream<int> calculate(int number) async* {
  for(int i = 0; i < 5; i++) {
    yield i * number;
    
    await Future.delayed(Duration(seconds: 1));
  }
}
```
```
0
1
2
3
4
0
1000
2000
3000
4000
```