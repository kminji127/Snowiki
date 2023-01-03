# Python

# 자료형

## 정수

`int()`

양의 정수, 음의 정수, 0

## 실수

`float()`

변수에 소수점을 붙이면 실수형 변수로 처리

소수부가 0이거나 정수부가 0인 소수는 0 생략 가능

- 5.0 ⇒ 5.
- -0.7 ⇒ -.7

**지수 표현 방식**

임의의 큰 수 표현 목적

e나 E 다음에 오는 수 = 10의 지수부

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/2923d09c-5778-4656-b342-c2bf0eeb5d3e/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20230102%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20230102T134036Z&X-Amz-Expires=86400&X-Amz-Signature=5b0921133b4ccb916b7f82c592fed22682cc413f16e93d950782fdfd1b521753&X-Amz-SignedHeaders=host&response-content-disposition=filename%3D%22Untitled.png%22&x-id=GetObject)

- ex) 1e9 = 10의 9제곱 = 10억

최단 경로 알고리즘에서는 도달할 수 없는 노드에 대하여 최단 거리를 무한(INF)로 설정하기도 함, 이때 가능한 최대값이 10억 미만이라면 무한의 값으로 1e9를 이용할 수 있음

**부정확성**

원인: 실수형을 저장하기 위해 4 또는 8바이트의 메모리만 할당 ⇒ 정확도 한계

- 2진수에서는 0.9를 표현할 때 미세한 오차 발생

권장: round() 함수로 소수점 반올림

- round(123.456, 2) = 123.46

### 수 자료형의 연산

- 나누기 연산자(/): 실수형을 결과로 반환
- 나머지 연산자(%)
- 몫 연산자(//)
- 거듭제곱 연산자(**)

![연산자 우선순위 (괄호: 0순위)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/11b50ee9-8986-4c33-bf90-66582b04686d/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20230102%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20230102T134109Z&X-Amz-Expires=86400&X-Amz-Signature=05d2861746455ca5d9265d605e7cda3f79370e3aa98f61d92b1bb78b1d9a7058&X-Amz-SignedHeaders=host&response-content-disposition=filename%3D%22Untitled.png%22&x-id=GetObject)

연산자 우선순위 (괄호: 0순위)

## 문자열

`str()`

- 초기화: 큰따옴표(”) 또는 작은따옴표(’)
- 문자열 안에 따옴표 들어갈 경우
    - 전체 문자열을 큰따옴표로 구성 ⇒ 내부적으로 작은따옴표 가능
    - 전체 문자열을 작은따옴표로 구성 ⇒ 내부적으로 큰따옴표 가능
    - 백슬래시(\) 사용
- 문자열 연결(Concatenate): 덧셈(+) 사용
- 문자열 변수를 양의 정수과 곱하면 그 값만큼 여러 번 더해짐
- 인덱싱, 슬라이싱 가능, But 특정 인덱스의 값 수정 불가 (Immutable)
- 제어 문자(escape sequence)
    
    ![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/e272d54b-68f2-4fc3-8df4-2d27e1529a8b/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20230102%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20230102T134142Z&X-Amz-Expires=86400&X-Amz-Signature=58610538a8ac5479e98914727bceca8a95d461d2093794f2267440312a19a073&X-Amz-SignedHeaders=host&response-content-disposition=filename%3D%22Untitled.png%22&x-id=GetObject)
    

## 리스트 (또는 배열, 테이블)

- C, Java에서의 배열(Array)의 기능 및 연결 리스트와 유사한 기능을 지원
- C++의 STL vector와 기능적으로 유사
- [] 안에 원소 삽입
- 쉼표(,)로 원소 구분
- 어떠한 자료형도 포함시킬 수 있음
- 비어있는 리스트 선언: list() 또는 []
- 원소 접근: 인덱스 값을 괄호에 넣음 (0부터 시작)
    - list[3]

```python
# 크기가 n이고 모든 값이 0인 1차원 리스트 초기화
n = 10
list = [0] * n
print(list) # [0,0,0,0,0,0,0,0,0,0]
```

### 인덱싱

특정 원소에 접근

- 양의 정수 : index[n] = n+1번째 원소
- 음의 정수 : index[-n] = 원소를 거꾸로 탐색 (뒤에서 n번째 원소)

### 슬라이싱

리스트에서 연속적인 위치를 갖는 원소 가져옴

대괄호 안에 콜론(:)으로 시작~끝 인덱스 설정

index[a:b] = [a,b) = 인덱스 a부터 b-1까지

### 리스트 컴프리헨션

리스트 초기화 방법 중 하나

대괄호([]) 안에 조건문과 반복문을 적용

특히 N * M 크기의 2차원 리스트를 초기화할 때 효과적

```python
# 일반적인 코드
array = []
for i in range(10): # 0 이상 10 미만
    if i % 2 == 1:
        array.append(i)
print(array)

# 리스트 컴프리헨션
array = [i for i in range(10)]
print(array) # [0,1,2,3,4,5,6,7,8,9]

array = [i for i in range(10) if i % 2 == 1]
print(array) # [1,3,5,7,9]

array = [i*i for i in range(1, 10)] # 1 이상 10 미만 수의 제곱값
print(array) # [1, 4, 9, 16, 25, 36, 49, 64, 81]

n = 3
m = 5
[[0]*n for _ in range(m)] # [[0, 0, 0], [0, 0, 0], [0, 0, 0], [0, 0, 0], [0, 0, 0]]
[[0]*n] * m # 잘못된 예시. 전체 리스트 안에 포함된 각 리스트가 모두 같은 객체로 인식됨
```

### 관련 메소드

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/5ab7dbcd-5599-49d9-931f-c41ce7f1ed15/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20230102%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20230102T134234Z&X-Amz-Expires=86400&X-Amz-Signature=47f075cfe28fea01f258dc43c5481286783d267bad401a0ebf5a40561de3c5cf&X-Amz-SignedHeaders=host&response-content-disposition=filename%3D%22Untitled.png%22&x-id=GetObject)

```python
a = [1,2,3,4,5,5,5]
remove_set = {3,5} # 집합 자료형

# remove_set에 포함되지 않은 값만을 저장
result = [i for i in a if i not in remove_set]
print(result) # [1,2,4]
```

## 튜플

리스트와 유사하지만 문법적 차이 존재

- 한 번 선언된 값 변경 불가
- 리스트는 대괄호(`[]`), 튜플은 소괄호(`()`)
- 상대적으로 기능 제한적, 적은 메모리 사용 ⇒ 공간 효율적

```python
t1 = (1,2,3,4,5,6,7,8,9)
len(t1) # 9
print(t1[3]) # 4
print(t1[1:4]) # (2,3,4)
t1[2] = 7 # TypeError

t2 = (1,) # 1개의 요소만을 가질 때도 요소 뒤에 콤마(,)를 반드시 붙여야 한다
t3 = 1, 2, 3 # 괄호 생력 가능
```

**사용하면 좋은 경우**

- 서로 다른 성질의 데이터를 묶어서 관리해야 할 때
    - 최단 경로 알고리즘: (비용, 노드번호)의 형태로 튜플 자료형 사용
    - 데이터의 나열을 해싱(Hashing)의 키 값으로 사용할 때
        - 튜플은 변경 불가능하므로
    - 리스트보다 메모리 효율적으로 사용해야 할 때

## 사전

키(Key)와 값(Value)의 쌍을 데이터로 가지는 자료형

- 값을 순차적으로 저장하는 리스트, 튜플과 대비
- 원하는 **변경 불가능한(Immutable)** 자료형을 키로 사용 가능
- 해시 테이블(Hash Table)을 이용 ⇒ 데이터 조회/수정 처리 시간 O(1)

## 집합

- 중복 허용 X
- 순서 없음
- 리스트 또는 문자열을 이용하여 초기화: set() 함수
- 또는 중괄호(`{}`) 안에 원소를 콤마 기준으로 삽입하여 초기화
- 데이터 조회/수정 처리 시간 O(1)
- 집합 연산: 합집합(`|`), 교집합(`&`), 차집합(`-`)

```python
data = set([1,2,3,3,4,5]) # {1,2,3,4,5}
data = {1,1,2,3,4,4,5} # {1,2,3,4,5}
```

### 관련 함수

- add(n): 값이 n인 원소 추가
- update([m,n]): 원소 여러 개 추가
- remove(n): 값이 n인 원소 삭제

## 자료형 특징

- 리스트, 튜플: 순서 있음, 인덱싱으로 자료형 값에 접근 가능
- 사전, 집합: 순서 없음, 인덱싱 불가, 사전의 키 또는 집합의 원소를 이용해 O(1)의 시간 복잡도로 조회
    - 변경 불가능한 값 또는 객체

## 번외: 언더바(_)

용도: 반복을 수행하되 반복을 위한 변수 값을 무시하고자 할 때

```python
for _ in range(3):
    print("Hello")
# Hello
# Hello
# Hello
```

**[기타 역할](https://tibetsandfox.tistory.com/20)**

- 인터프리터에서의 마지막 값
- 무시하는 값
- 숫자열의 자릿수 구분
- 네이밍
    - 앞에 하나 붙은 경우 (`_variable`): 모듈 내에서만 해당 변수/함수를 사용하겠다.
        - But, 완전한 private는 아니기 때문에 직접 가져오거나 호출하면 사용 가능
    - 뒤에 하나 붙은 경우 (`variable_`): 파이썬 키워드와 변수/함수명의 충돌 방지
    - 앞에 두 개 붙은 경우 (`__variable`): [네임 맹글링](https://tibetsandfox.tistory.com/21)(해당 변수/함수의 이름을 파이썬이 바꿔버림) ⇒ 본연의 이름으로 접근 불가
    - 앞뒤로 두 개씩 붙은 경우 (`__variable__`): 파이썬이 정의한 변수/함수에 사용되는 네이밍 룰. 대부분 오버라이딩할 때 사용됨 = 매직/던더 메소드
        - __init__ 함수: 클래스의 인스턴스가 생성될 때 가장 처음으로 실행되는 함수 = 생성자 역할
    

# 기본 입출력

## 입력

- `input()`: 한 줄의 문자열 입력받음
    - 항상 문자열로 반환
- `split("문자")`: 문자열을 특정한 문자를 기준으로 자름 (공백이면 띄어쓰기 기준) ⇒ 리스트로 반환
- `map(함수, 리스트)`: 리스트의 모든 원소에 각각 특정한 함수 적용
    - `list(map(int, input().split()))`: 공백 기준으로 구분된 데이터 입력받을 때
    - `a, b, c = map(int, input().split())`: 공백 기준으로 구분된 데이터 개수가 적을 때

```python
# 데이터의 개수 입력
n = int(input())

# 각 데이터를 공백을 기준으로 구분하여 입력
data = list(map(int, input().split()))
x, y, z = list(map(int, input().split()))

# 내림차순 정렬
data.sort(reverse=True)
print(data)
print(x, y, z)
```

**빠르게 입력받기**

- `sys.stdin.readline()` 함수 이용
- 단, 입력 후 엔터가 줄 바꿈 기호로 입력되므로 `rstrip()` 메소드를 함께 이용

```python
import sys

data = sys.stdin.readline().rstrip()
print(data)
```

## 출력

- `print()`: 각 변수를 콤마(,)를 이용하여 띄어쓰기로 구분
    - 기본적으로 출력 후 줄바꿈을 수행
    - 원치 않는 경우 end 속성 이용
    - [기타 옵션](https://infinitt.tistory.com/11): 구분자 sep, format 등
    
    ```python
    a = 1
    b = 2
    print(a, b) # 1 2
    print(7, end=" ")
    print(8, end=" ") # 7 8
    print(a, b, sep=";") # a;b
    ```
    
- [문자열 포매팅](https://blockdmask.tistory.com/424)
    - 내장함수 `format`
        - format(값, 바꾸고 싶은 형식)
    - `%`와 서식기호 사용
        - `%s`(문자열), `%d`(정수), `%f`(실수), `%o`(8진수), `%x`(16진수), `%%`(문자 % 표현)
    - f-string
        - 문자열 앞에 접두사 f를 붙임
        - 중괄호 안에 변수명 기입. 문자열 안에 넣을 수 있음

```python
# format
age = 20
print('name: {0}, age: {1}'.format('sm', age)) # 직접 대입
print('number: {num}, gender: {gen}'.format(num=sm, gen='여')) # 이름으로 대입
print( format(3.14159, ".2f") ) # 3.14

# % 서식 기호
name = "john"
age = 31
print('my name is %s' % name) # my name is john
print('name: %s, age: %d' % (name, age))
print('%x' % age) # 16진수로 변환

# f-string
answer = 7
print("정답은 " + str(answer) + "입니다.") # 정답은 7입니다.
print(f"정답은 {answer}입니다.")
```

# 조건문

if ~ elif ~ else

- if: 조건문 1이 True일 때
- elif: 조건문 1이 False이고, 조건문 2가 True일 때
- else: 위의 모든 조건문이 False일 때

### `pass` 키워드

아무것도 처리하고 싶지 않을 때 그냥 넘어감

```python
score = 85 # B

if score >= 90:
  print("A")
elif score >= 80:
  print("B")
elif score >= 70:
  print("C")
elif score >= 60:
  pass
else:
  print("F")

# 조건부 표현식: if~else 문을 한 줄에 작성
result = "Success" **if score >= 80** else "Fail"
print(result)
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/0776b4a2-97de-4af7-b964-ce762decd87f/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20230102%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20230102T134342Z&X-Amz-Expires=86400&X-Amz-Signature=840217c86c2f8a38522a2084ae44bbd616192fb94333f926e77535f777aca0b9&X-Amz-SignedHeaders=host&response-content-disposition=filename%3D%22Untitled.png%22&x-id=GetObject)

### 비교 연산자

- `==`: 서로 같음 (대입 연산자 `=`와 다름)
- `!=`: 서로 다름
- `>`: ~보다 큼 (초과)
- `<`: ~보다 작음 (미만)
- `>=`: ~보다 크거나 같음 (이상)
- `<=`: ~보다 작거나 같음 (이하)

### 논리 연산자

- A `and` B (곱셈 / 교집합): 모두 참일 때 True
- A `or` B (덧셈 / 합집합): 둘 중 하나만 참이라도 True
- `not` X: X가 거짓일 때 True

### 멤버십 연산자

- x `in` 리스트: 리스트 안에 x가 포함될 때 True
- x `not in` 문자열: 문자열 안에 x가 포함되지 않을 때 True

# 반복문

## while문

실행문이 True인 동안 반복적으로 실행

```python
i = 1
result = 0

while i <= 9:
  if i % 2 == 1:
    result += i
  i += 1

print(result) # 25

i = 1
while True:
  print("i =", i) # 1~5까지 출력
  if i == 5:
    break
  i += 1
```

## for문

`for 변수 in 리스트`: in 뒤에 오는 데이터(리스트, 튜플 등)의 원소를 순차적으로 방문

### `continue` 키워드

남은 코드의 실행을 건너뛰고 다음 반복을 진행

### `break` 키워드

반복문 즉시 탈출

```python
array = [9,8,7,6,5]
for x in array:
  print(x)

result = 0
for i in range(1, 10): # 1부터 9까지
  result += i
print(result) # 45

result = 0
for i in range(1, 10):
  if i % 2 == 0:
    continue
  result += i
print(result) # 25

scores = [90, 85, 77, 65, 97]
cheating_list = {2, 4}
for i in range(5):
  if i+1 in cheating_list:
    continue
  if scores[i] >= 80:
    print(i+1, "번 학생 합격") # 1, 5번 합격

# 중첩 for문으로 구구단 출력
for i in range(2, 10):
  for j in range(1, 10):
    print(i, "x", j, "=", i*j)
  print()
```

# 함수

특정한 작업을 하나의 단위로 묶어놓은 것

- [내장 함수](https://wikidocs.net/32): 파이썬이 기본적으로 제공
- 사용자 정의 함수

```python
def 함수명(매개변수 parameter):
  실행할 코드
  return 반환값

함수명(인자 argument) # 함수 사용
```

- 매개변수: 함수 내부에서 사용할 변수
- 인자: 함수 호출할 때 넣는 값

```python
def add(a, b):
  print("덧셈 결과 =", a+b)

add(2, 4)
add(b=2, a=3)
```

### `global` 키워드

함수 내 지역변수가 아닌, 함수 바깥에 선언된 변수를 바로 참조

```python
a = 0
def func():
  global a
  a += 1

for i in range(10):
  func()

print(a) # 10
```

**여러 개의 반환 값**

```python
def operator(a, b):
  add_var = a + b
  subtract_var = a - b
  multiply_var = a * b
  divide_var = a / b
  return add_var, subtract_var, multiply_var, divide_var

a, b, c, d = operator(7, 3)
print(a, b, c, d)
```

### 람다 표현식

함수를 한 줄에 간단하게 작성

이름 없는 함수

lambda 매개변수: 리턴값

```python
 # 일반적인 add() 메서드
def add(a, b):
  return a + b
print(add(2, 6))

# 람다 표현식
print((lambda a,b: a+b)(3,7))

array = [('홍길동', 50), ('이순신', 32), ('아무개', 74)]

def my_key(x):
  return x[1]

# sorted 함수로 오름차순 정렬 (점수 기준)
print(sorted(array, key=my_key))
print(sorted(array, key=lambda x: x[1]))
```

- `sorted(iterable)`: 입력값을 정렬한 후 그 결과를 리스트로 돌려주는 함수
    - key: 정렬 기준

```python
# 여러 개의 리스트에 적용
list1 = [1,2,3,4,5]
list2 = [6,7,8,9,10]

result = list(map(lambda a,b: a+b, list1, list2))
print(result) # [7, 9, 11, 13, 15]
```

# 표준 라이브러리

[https://docs.python.org/3/library/index.html](https://docs.python.org/3/library/index.html)

- [내장 함수](https://wikidocs.net/32): 입출력, 정렬 등 기본적인 함수
- itertools: 반복되는 형태의 데이터를 처리하기 위한 기능
    - 순열, 조합 라이브러리가 자주 사용됨 ⇒ 완전 탐색
        
        ![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/ac23da02-9ff2-4dec-b48a-754f42a3831a/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20230102%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20230102T134430Z&X-Amz-Expires=86400&X-Amz-Signature=49df02240c35006789be67201a9bfe2c2e0820050c3766eb53232953ad1fd915&X-Amz-SignedHeaders=host&response-content-disposition=filename%3D%22Untitled.png%22&x-id=GetObject)
        
    
    ```python
    from itertools import permutations
    from itertools import combinations
    from itertools import product
    from itertools import combinations_with_replacement
    
    data = ['A', 'B', 'C']
    
    # 순열
    print(list(permutations(data, 2)))
    
    # 조합
    print(list(combinations(data, 2)))
    
    # 중복순열
    print(list(product(data, repeat=2)))
    
    # 중복조합
    print(list(combinations_with_replacement(data, 2)))
    ```
    
- heapq: 힙(heap) 자료구조 제공
    - 보통 우선순위 큐 기능 구현 목적으로 사용됨 ⇒ 최단 경로 알고리즘
- bisect: 이진 탐색(Binary Search) 기능 제공
- collections: 덱(deque), 카운터(Counter) 등 자료구조
    - Counter: 등장 횟수를 세는 기능
        - 리스트 같이 반복 가능한(iterable) 객체에서, 내부의 원소가 몇 번씩 등장했는지 알려줌
    
    ```python
    from collections import Counter
    
    cnt = Counter(['red', 'blue', 'red', 'green', 'blue', 'blue'])
    
    print(cnt['blue']) # 3
    print(cnt['green']) # 1
    print(dict(cnt)) # {'red': 2, 'blue': 3, 'green': 1}
    ```
    
- math: 팩토리얼, 제곱근, 최대공약수(gcd), 삼각함수, 파이(pi) 등 수학적 기능
    
    ```python
    import math
    
    def lcm(a, b):
      return a * b // math.gcd(a, b)
    
    x = 21
    y = 14
    print(math.gcd(x, y)) # 최대 공약수
    print(lcm(x, y)) # 최소 공배수
    ```