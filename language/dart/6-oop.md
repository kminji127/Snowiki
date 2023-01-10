# Object Oriented Programming

## 클래스, 인스턴스 생성
```dart
void main() {
  // 인스턴스 생성
  Idol blackPink = const Idol('블랙핑크', ['지수', '제니', '리사', '로제']);
  print(blackPink.name);
  print(blackPink.members);
  blackPink.sayHello();
  blackPink.introduce();
  
  Idol bts = const Idol('BTS', ['RM', '진', '슈가', '제이홉', '지민', '뷔', '정국']);
  print(bts.name);
  print(bts.members);
  bts.sayHello();
  bts.introduce();
  
  Idol idol = Idol.fromList([
    ['멤버1', '멤버2', '멤버3'],
    '아이돌',
  ]);
  print(idol.name);
  print(idol.members);
  idol.sayHello();
  idol.introduce();
}

class Idol {
  // immutable
  final String name;
  final List<String> members;
  
  // 생성자
//   Idol(String name, List<String> members): 
//     // this: 현재 클래스
//     this.name = name,
//     this.members = members;
  
  // 간단한 생성자 생성
  const Idol(this.name, this.members);
  
  // named 생성자
  Idol.fromList(List values):
    this.members = values[0],
    this.name = values[1];
  
  void sayHello() {
    print('안녕하세요 ${this.name}입니다.');
  }
  
  void introduce() {
    print('저희 멤버는 ${this.members}가 있습니다.');
  }
}
```

## getter, setter
- getter: 데이터를 가져올 때
- setter: 데이터를 설정할 때

```dart
void main() {
  // 인스턴스 생성
  Idol blackPink = Idol('블랙핑크', ['지수', '제니', '리사', '로제']);
  Idol bts = Idol('BTS', ['RM', '진', '슈가', '제이홉', '지민', '뷔', '정국']);
  
  print(blackPink.firstMember);
  print(bts.firstMember);
  
  blackPink.firstMember = '아무개';
  print(blackPink.members);
}

class Idol {
  // immutable
  String name;
  List<String> members;
  
  // 간단한 생성자 생성
  Idol(this.name, this.members);
  
  ...
  
  // getter
  String get firstMember {
    return this.members[0];
  }
  
  // setter
  set firstMember(String name) {
    this.members[0] = name;
  }
}
```

## private
- 클래스 이름 앞에 _(언더바) 붙임

## Inheritance(상속)
- 부모 클래스의 모든 속성을 자식 클래스가 부여받음

```dart
void main() {
  print('========idol=========');
  Idol apink = Idol(name: '에이핑크', membersCount: 5);
  apink.sayName();
  apink.sayMembersCount();
//   apink.sayMale(); // error
  
  print('========BoyGroup=========');
  BoyGroup bts = BoyGroup('BTS', 7);
  bts.sayName();
  bts.sayMembersCount();
  bts.sayMale();
  
  print('========GirlGroup=========');
  GirlGroup redVelvet = GirlGroup('Red Velvet', 5);
  redVelvet.sayName();
  redVelvet.sayMembersCount();
  redVelvet.sayFemale();
  
  print('=========type comparison========');
  print(apink is Idol); // true
  print(apink is BoyGroup); // false
  print(bts is Idol); // true
  print(bts is BoyGroup); // true
}

// 부모 클래스
class Idol {
  String name;
  int membersCount;
  
  Idol({
    required this.name,
    required this.membersCount,
  });
  
  void sayName() {
    print('저는 ${this.name}입니다.');
  }
  
  void sayMembersCount() {
    print('${this.name}은/는 ${this.membersCount}명의 멤버가 있습니다.');
  }
}

// 자식 클래스
class BoyGroup extends Idol {
  BoyGroup(
    String name,
    int membersCount,
  ) : super(
    name: name,
    membersCount: membersCount,
  );
  
  void sayMale() {
    print('저는 남자 아이돌입니다.');
  }
}

// 자식 클래스
class GirlGroup extends Idol {
  GirlGroup(
    String name,
    int membersCount,
  ) : super(
    name: name,
    membersCount: membersCount,
  );
  
 void sayFemale() {
    print('저는 여자 아이돌입니다.');
  }  
}
```

## Method Overriding
- method: function(class 내부에 있는 함수)
- override: 덮어쓰다(우선시하다)

```dart
void main() {
  TimesTwo tt = TimesTwo(3);
  print(tt.calculate());
  
  TimesFour tf = TimesFour(3);
  print(tf.calculate());
  
}

// 부모 클래스
class TimesTwo {
  final int number;
  
  TimesTwo(this.number);
  
  //method
  int calculate() {
    return number * 2;
  }
}

// 자식 클래스
class TimesFour extends TimesTwo {
  TimesFour(int number) : super(number);
  
  @override
  int calculate() {
//     return number * 4;
    return super.calculate() * 2;
  }
  
}
```

## static
- 인스턴스에 귀속되지 않고 클래스에 귀속됨

```dart
void main() {
  Employee lisa = Employee('리사');
  Employee jisoo = Employee('지수');
  
  // 인스턴스에 귀속
  lisa.name = '제니';
  lisa.printNameAndBuilding();
  jisoo.printNameAndBuilding();
  
  // 클래스에 귀속
  Employee.building = '오투타워';
  lisa.printNameAndBuilding();
  jisoo.printNameAndBuilding();
  Employee.printBuilding();
}

class Employee {
  static String? building;
  String name;
  
  Employee(this.name);
  
  void printNameAndBuilding() {
    print('이름: $name, 근무지: $building');
  }
  
  static void printBuilding() {
    print('저희는 $building 건물에서 근무중입니다.');
  }
}
```

## interface, abstract
```dart
void main() {
  BoyGroup bts = BoyGroup('BTS');
  GirlGroup redVelvet = GirlGroup('레드벨벳');
//   IdolInterface test = IdolInterface('테스트'); // 인스턴스화 불가
  
  bts.sayName();
  redVelvet.sayName();
}

// interface
abstract class IdolInterface {
  String name;
  
  IdolInterface(this.name);
  
  void sayName();
}

class BoyGroup implements IdolInterface {
  String name;
  
  BoyGroup(this.name);
  
  void sayName() {
    print('제 이름은 $name입니다.');
  }
}

class GirlGroup implements IdolInterface {
  String name;
  
  GirlGroup(this.name);
  
  void sayName() {
    print('제 이름은 $name입니다.');
  }
}
```

## Generic
- 타입을 변수처럼 외부에서 받을 때

```dart
void main() {
  Lecture<String> lecture1 = Lecture('123', 'lecture1');
  lecture1.printIdType();
  
  Lecture<int> lecture2 = Lecture(123, 'lecture1');
  lecture2.printIdType();
}

class Lecture<T> {
  final T id;
  final String name;
  
  Lecture(this.id, this.name);
  
  void printIdType() {
    print(id.runtimeType);
  }
}
```