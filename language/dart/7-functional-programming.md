# Functional Programming

## Type 변환
- Map: `asMap()`
- Set: `toSet()`
```dart
List<String> blackPink = ['로제', '지수', '리사', '제니', '제니'];
print(blackPink.asMap());
print(blackPink.toSet());

Map blackPinkMap = blackPink.asMap();
print(blackPinkMap.keys.toList());
print(blackPinkMap.values.toList());

Set blackPinkSet = Set.from(blackPink);
print(blackPinkSet.toList());
```

## map()
```dart
// List Mapping
List<String> blackPink = ['로제', '지수', '리사', '제니'];

final newBlackPink = blackPink.map((x) {
  return '블랙핑크 $x';
});
print(newBlackPink.toList());

final newBlackPink2 = blackPink.map((x) => '블랙핑크 $x');
print(newBlackPink2.toList());

print(newBlackPink == newBlackPink2); // false

String number = '13579';
final parsed = number.split('').map((x) => '$x.jpg').toList();
print(parsed); // [1.jpg, 3.jpg, 5.jpg, 7.jpg, 9.jpg]


// Map Mapping
Map<String, String> harryPotter = {
  'Harry Potter': '해리 포터',
  'Ron Weasley': '론 위즐리',
  'Hermione Granger': '헤르미온느 그레인저',
};

final result = harryPotter.map((key, value) => MapEntry(
  'Harry Potter Character $key',
  '해리포터 캐릭터 $value',
));
print(result);

final keys = harryPotter.keys.map((x) => 'HPC $x').toList();
final values = harryPotter.values.map((x) => '해리포터 $x').toList();


// Set Mapping
Set blackPinkSet = {'로제', '지수', '제니', '리사'};
final newSet = blackPinkSet.map((x) => '블랙핑크 $x').toSet();
print(newSet);
```

## where()
- **필터링** 기능

```dart
List<Map<String, String>> people = [
  {
    'name': '로제',
    'group': '블랙핑크'
  },
  {
    'name': 'RM',
    'group': 'BTS'
  },
  {
    'name': '제니',
    'group': '블랙핑크'
  },
  {
    'name': '슬기',
    'group': '레드벨벳'
  },
];

final blackPink = people.where((x) => x['group'] == '블랙핑크').toList();
final bts = people.where((x) => x['group'] == 'BTS').toList();
print(blackPink);
print(bts);
```

## reduce()
- 같은 타입만을 리턴해야 함

```dart
List<int> numbers = [1, 3, 5, 7, 9];

final result = numbers.reduce((prev, next) {
  print('--------------');
  print('previous: $prev');
  print('next: $next');
  print('total: ${prev + next}');
  
  return prev + next;
});
print(result);

List <String> words = [
  '안녕하세요 ',
  '저는 ',
  '코드팩토리입니다.',
];

final sentence = words.reduce((prev, next) => prev + next);
print(sentence);
```

## fold()
- 다른 타입 리턴 가능

```dart
List<int> numbers = [1, 3, 5, 7, 9];

final sum = numbers.fold<int>(0, (prev, next) {
  print('-----------');
  print('prev: $prev');
  print('next: $next');
  print('total: ${prev + next}');
  
  return prev + next;
});
print(sum);

List <String> words = [
  '안녕하세요 ',
  '저는 ',
  '코드팩토리입니다.',
];

final sentence = words.fold<String>('', (prev, next) => prev + next);
print(sentence);

final count = words.fold<int>(0, (prev, next) => prev + next.length);
print(count);
```

## cascading operator
```dart
void main() {
  List<int> even = [2, 4, 6, 8];
  List<int> odd = [1, 3, 5, 7];
  print([...even, ...odd]); // [2, 4, 6, 8, 1, 3, 5, 7]

  List<Map<String, String>> people = [
    {'name': '로제', 'group': '블랙핑크'},
    {'name': 'RM', 'group': 'BTS'},
    {'name': '제니', 'group': '블랙핑크'},
    {'name': '슬기', 'group': '레드벨벳'},
  ];

  final parsedPeople = people.map((x) => Person(
        name: x['name']!,
        group: x['group']!,
      )).toList();
  
  print(parsedPeople);
  
  for(Person person in parsedPeople) {
    print(person.name);
    print(person.group);
  }
  
  final bts = parsedPeople.where((x) => x.group == 'BTS');
  print(bts);
}

class Person {
  final String name;
  final String group;

  Person({
    required this.name,
    required this.group,
  });
  
  @override
  String toString() {
    return 'Person(name: $name, group: $group)';
  }
}
```