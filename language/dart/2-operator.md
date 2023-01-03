# Operator

## 숫자 연산자
```dart
int? number = 2;

number ++;
print(number); // 3

number --;
print(number); // 2

number += 2;
print(number); // 4

number = null;
number ??= 3; // null이면 3
print(number);
```

## 비교 연산자
```dart
int num1 = 1;
int num2 = 2;

print(num1 < num2);
print(num1 > num2);
print(num1 <= num2);
print(num1 >= num2);
print(num1 == num2);
print(num1 != num2);

print(num1 is int); // true
print(num1 is String); // false
print(num1 is! int); // false
print(num1 is! String); // true
```

## 논리 연산자
```dart
// and - &&
print(12 > 10 && 1 > 0); // true
print(12 > 10 && 1 < 0); // false

// or - ||
print(12 > 10 || 1 < 0); // true
print(12 < 10 || 1 < 0); // false
```
