# Basic Concept

## 변수(Variable)

[variable.md](variable.md "mention")

변수(Variable)는 값(value)을 저장(할당)하고 그 저장된 값을 참조하기 위해 사용한다. 한번 쓰고 버리는 값이 아닌 **유지(캐싱)할 필요가 있는 값**은 변수에 담아 사용한다.

변수는 **위치(주소)를 기억하는 저장소**이다. 위치란 메모리 상의 주소(address)를 의미한다. 즉, 변수란 메모리 주소(Memory address)에 접근하기 위해 사람이 이해할 수 있는 언어로 지정한 식별자(identifier)이다.

변수를 정의하면 메모리에 포인터가 생긴다. 변수가 가리키는 곳에 값이 들어간다. 재할당 가능(mutable)\
`let` (added in ES6): 자바스크립트에서 변수를 선언하는 키워드\
예전에는 `var`를 사용했으나, 지금은 사용 안 함

* var hoisting: 선언 위치에 상관 없이 제일 위로 끌어올리는 것
* block scope을 무시함

Global Scope: 코드 전체\
Block Scope: 코드 블록 내부\
Function Scope: 함수 내부

## Constants

`const`\
값을 한 번 할당하면 변경 안 됨\
favor immutable data type always

* security
* thread safety
* reduce human mistakes

## Variable types

* **원시 타입** (primitive data type), single item: number, string, boolean, null, undefined, symbol
  * passed by value (값에 의한 전달)
  * immutable value (메모리 영역에서의 변경이 불가능한 값)
  * 재할당은 가능
* **객체 타입** (Object data type), box container
  * passed by reference (참조에 의한 전달)
  * mutable value (변경 가능한 값)
* function, first-class function

C나 Java와는 다르게 변수를 선언할 때 데이터 타입을 미리 지정하지 않는다. 다시 말해, 변수에 할당된 값의 타입에 의해 동적으로 변수의 타입이 결정된다. 이를 **동적 타이핑(Dynamic Typing)**이라 하며 자바스크립트가 다른 프로그래밍 언어와 구별되는 특징 중 하나이다.

* Immutable 데이터 타입: 데이터 자체를 변경하지 못함
  * primitive types, frozen objects
* Mutable 데이터 타입: 변경 가능
  * all objects by default are mutable in JS

## 연산자(Operator)

[operator.md](operator.md "mention")

하나 이상의 표현식을 대상으로 산술, 할당, 비교, 논리, 타입 연산 등을 수행해 하나의 값을 만든다. 이때 연산의 대상을 피연산자(Operand)라 한다.\
_operator.js 참조_

## 함수(Function)

[function.md](function.md "mention")

어떤 작업을 수행하기 위해 필요한 문(statement)들의 집합을 정의한 코드 블록이다. 함수는 이름과 매개변수를 가지며 필요한 때에 호출하여 코드 블록에 담긴 문들을 일괄적으로 실행할 수 있다.

```javascript
// 함수 선언문
function name(param) { // 기본 함수
  return param * param;
}

const nfunc = function() { // 함수 표현식(Anonymous function)
  return param * param;
};

const nfunc = function name() { // 함수 표현식(Named function)
  return param * param;
};

const name = (param) => { // Arrow function
  param * param;
  return;
};

(function name(param) { // IIFE (즉시 실행 함수)
  return param * param;
})();

// 함수 호출
name(2); // 4
```

**콜백(CallBack) 함수**: 인자로 사용되는 함수

* 동기(Synchronous) 함수: 호출부에서 실행 결과가 리턴될 때 까지 기다려야 하는 함수
* 비동기(Asynchronous) 함수: 쉽게 설명하면 호출부에서 실행 결과를 가다리지 않아도 되는 함수
* 콜백 함수를 통한 비동기 처리

```javascript
function findUserAndCallBack(id, cb) {
  setTimeout(function () {
    console.log("waited 0.1 sec.");
    const user = {
      id: id,
      name: "User" + id,
      email: id + "@test.com",
    };
    cb(user);
  }, 100);
}

findUserAndCallBack(1, function (user) {
  console.log("user:", user);
});
```

* 콜백 지옥: 콜백 함수가 계속 중첩되는 것 -> `Promise`나 `async/await`을 통해 가독성을 높인 비동기 처리 (참고 자료: [https://www.daleseo.com/js-async-promise/](https://www.daleseo.com/js-async-promise/))
* **Promise**: 비동기 작업이 맞이할 미래의 완료 또는 실패와 그 결과 값

```javascript
findUser(1)
  .then((user) => console.log("user:", user)); // 결과값을 담은 콜백함수를 인자로    
  .catch((error) => console.log("실패:", error)); // 예외 처리 로직을 담은 콜백 함수를 인자로

function findUser(id) {
  return new Promise(function (resolve) {
    setTimeout(function () {
      console.log("waited 0.1 sec.");
      const user = {
        id: id,
        name: "User" + id,
        email: id + "@test.com",
      };
      resolve(user);
    }, 100);
  });
}
```

* **async/await**: 비동기 코드를 마치 동기 코드처럼 보이게 작성 가능. 가독성 있는 여러 개의 Promise 중첩 호출 코드 작성 가능
  * await: 비동기 함수가 리턴하는 Promise로부터 결과값을 추출. 일반 비동기 처리처럼 바로 실행이 다음 라인으로 넘어가는 것이 아니라 결과값을 얻을 수 있을 때까지 대

```javascript
async function fetchAuthorName(postId) {
  const postResponse = await fetch(
    `https://jsonplaceholder.typicode.com/posts/${postId}`
  );
  const post = await postResponse.json();
  const userId = post.userId;
  const userResponse = await fetch(
    `https://jsonplaceholder.typicode.com/users/${userId}`
  );
  const user = await userResponse.json();
  return user.name;
}

fetchAuthorName(1).then((name) => console.log("name:", name));
```



Java에서의 `this`는 인스턴스 자신을 가리키는 참조변수이다. 이와 달리 자바스크립트는 함수를 호출할 때 함수가 어떻게 호출되었는지에 따라 `this`에 바인딩할 객체가 동적으로 결정된다. 함수를 호출하는 방식은 다음과 같다.

```javascript
var foo = function () {
  console.dir(this);
};

// 1. 함수 호출
foo(); // window
// window.foo();
this === window // in Browser console
this === global // in server-side(Node.js)

// 2. 메소드 호출
// this는 메소드를 호출한 객체에 바인딩됨
var obj = { foo: foo };
obj.foo(); // obj

// 3. 생성자 함수 호출
// 빈 객체 생성, this 바인딩 -> 동적 프로퍼티 생성 -> 생성된 객체 반환
var instance = new foo(); // instance

// 4. apply/call/bind 호출
var bar = { name: 'bar' };
foo.call(bar);   // bar
foo.apply(bar);  // bar
foo.bind(bar)(); // bar
```

## 객체(Object)

[object.md](object.md "mention")

원시 타입(Primitives)을 제외한 나머지 값들(함수, 배열, 정규표현식 등)은 모두 객체이다.

자바스크립트 객체는 **키(이름)와 값**으로 구성된 `프로퍼티(property)`의 집합이다. 프로퍼티의 값으로 자바스크립트에서 사용할 수 있는 모든 값을 사용할 수 있다. 자바스크립트의 함수는 일급 객체이므로 값으로 취급할 수 있다. 따라서 프로퍼티 값으로 함수를 사용할 수도 있으며 프로퍼티 값이 함수일 경우, 일반 함수와 구분하기 위해 메소드라 부른다.

```javascript
const str = "hello world!";
console.log(str.length); // 12
```

`str`의 프로퍼티에 접근하려고 할때 아래와 같은 순서로 접근이 된다.

* 자바스크립트는 임시 객체 `new String(str)`을 호출하여 원시 타입을 객체로 변환한다.
* 해당 객체는 `String` 메서드를 상속한다.
* 프로퍼티를 사용 후 참조가 해제될 경우 임시 객체는 메모리에서 회수 된다.

객체로 생성한 값과 원시값은 엄연히 다른 값이다.

`프로퍼티`는 객체의 구성원이라고 할 수 있다. 회사라는 객체에 구성원이 사원, 대리, 부장, 이사라고 한다면 이것들이 프로퍼티인 것이다. 프로퍼티 중 함수라서 실행이 가능한 것을 메서드라고 부른다. 프로퍼티에 접근을 하기 위해서는 두 가지 방법이 존재한다. 첫번째는 객체 이름, 마침표(.) 프로퍼티 이름으로 접근할 수 있다.

```javascript
const obj = { hello: 👋 }
obj.hello // 👋 
```

두번째로는 대괄호(\[])를 활용할 수 있다. 대괄호 안에 오는 표현식은 우선 평가된 후 문자열 타입이 아닌 경우 toString을 이용하여 문자열로 변경해 준다.

```javascript
const key = "hello"
const obj = { hello: 👋 }
obj[key] // 👋 
```
