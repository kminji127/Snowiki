# Statement

## if 문
```dart
int number = 18;
  
if(number % 3 == 0) {
  print('나머지가 0');
} else if(number % 3 == 1) {
  print('나머지가 1');
} else {
  print('나머지가 2');
  }
```

## switch 문
```dart
int number = 28;

switch(number % 3) {
  case 0:
    print('나머지가 0');
    break;
  
  case 1:
    print('나머지가 1');
    break;
    
  default:
    print('나머지가 2');
    break;
}
```

## 반복문

### for 문
```dart
int total = 0;
List<int> numbers = [1, 2, 3, 4, 5, 6];

// 방법 1
for (int i = 0; i < numbers.length; i++) {
  total += numbers[i];
}
print(total);

// 방법 2
total = 0;
for(int number in numbers) {
  total += number;
}
print(total);

for(int i = 0; i < 10; i++) {
  if (i % 2 == 0) {
    continue;
  }
  print(i); // 1 3 5 7 9
}
```

### while 문
```dart
int total = 0;
while(total < 10) {
  total += 1;
  
  if(total == 5) {
    break;
  }
}
print(total);
```

## enum
```dart
enum Status {
  approved,
  pending,
  rejected,
}

void main() {
  // 선언
  Status status = Status.pending;
  
  if (status == Status.approved) {
    print('승인');
  } else if (status == Status.pending) {
    print('대기');
  } else {
    print('거절');
  }
}
```