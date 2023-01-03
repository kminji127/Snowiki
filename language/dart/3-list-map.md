# List, Map, Set

## List
- `List<type> 변수명 = []`

```dart
List<String> google = ['flutter', 'gcp', 'android'];
List<int> numbers = [1, 2, 3, 4, 5];

// 인덱싱
print(google[0]); // 'flutter'
print(numbers[3]); // 4

// 리스트 길이
print(google.length); // 3

// 리스트에 값 추가, 제거
google.add('angular');
print(google);
google.remove('angular');
print(google);

// 인덱스 값 검색
print(google.indexOf('gcp')); // 1
```

## Map
- `Map<key_type, value_type> 변수명 = {key:value, key:value}`

```dart
Map<String, bool> isHarryPotter = {
  'Harry Potter' : true,
  'Ron Weasley' : true,
  'Hermione Granger' : true,
};

// 값 추가
isHarryPotter.addAll({
  'Spiderman' : true,
});
isHarryPotter['Hulk'] = false;

// 값 찾기
print(isHarryPotter['Ron Weasley']);

// 값 변경
isHarryPotter['Spiderman'] = false;

// 값 삭제
isHarryPotter.remove('Hulk');

// key, value 값 모음
print(isHarryPotter.keys);
print(isHarryPotter.values);
```

## Set
- `Set<type> 변수명 = {}`
- 중복 값 불가

```dart
final Set<String> names = {
  'Flutter',
  'Dart',
  'GCP',
  'Dart', // 중복 처리
};

// 값 추가, 삭제
names.add('angular');
names.remove('angular');

// 값 존재 여부 확인
print(names.contains('Flutter')); // true
print(names.contains('java')); // false

```