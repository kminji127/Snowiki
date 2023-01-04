# Function

- `(return type) 함수명 {}`
- optional parameter: `[]`

```dart
void main() {
  addNumbers(1, 2, 3 );
  print(addNumbers2(x:10, y:20, z:31));
  print(addNumbers3(10, y:20));

}

addNumbers(int x, int y, int z) {
  int sum = x + y + z;
  
  if (sum % 2 == 0) {
    print('짝수');
  } else {
    print('홀수');
  }
}

int addNumbers2({
  required int x,
  required int y,
  required int z,
}) {
  int sum = x + y + z;
  
  if (sum % 2 == 0) {
    print('짝수');
  } else {
    print('홀수');
  }
  
  return sum;
}

// arrow function
int addNumbers3(int x,{
  required int y,
  int z = 30,
}) => x + y + z;
```

## typedef
- 함수를 변수처럼 사용 가능 (`typedef 이름(파라미터)`)
- 함수를 미리 시그니처화해서 여러 함수를 유용하게 다룰 수 있음
```dart
void main() {
  Operation operation = add;
  int result = operation(10, 20, 30);
  print(result);
  
  operation = sub;
  int result2 = operation(10, 20, 30);
  print(result2);
  
  int result3 = cal(50, 20, 10, sub);
  print(result3);
}

// signature
typedef Operation = int Function(int x, int y, int z);

// 더하기
int add(int x, int y, int z) => x + y + z;

// 빼기
int sub(int x, int y, int z) => x - y - z;

int cal(int x, int y, int z, Operation operation) {
  return operation(x, y, z);
}
```