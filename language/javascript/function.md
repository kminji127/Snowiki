# Function

```javascript
// 려ㅜFunction
// - Object in JavaScript
//  - 하나의 함수에 하나의 역할
//  - 이름: doSomething, command, verb

// 1. 선언
// function name (param1, param2) { body ... return; }
function printHello(){
  console.log('Hello!');
}
printHello();

function log(message) {
  console.log(message);
}
log('Hello@');
log(1323);


// 2. 매개 변수(Parameter)
// - premitive parameter: passed by value
// - object parameter: passed by reference
function changeName(obj) {
  obj.name = 'coder';
}

const lucy = {name: 'lucy'};
changeName(lucy);
console.log(lucy);


// 3. Default Parameters (Added in ES6)
function showMessage(message, from){
  if(from === undefined){
    from = 'unknown';
  }
  console.log(`message: ${message} by ${from}`)
}

function showMessage2(message, from = '익명'){ // 디폴트 값 설정
  if(from === undefined){
    from = 'unknown';
  }
  console.log(`message: ${message} by ${from}`)
}
showMessage2('Hi');


// 4. Rest parameters (Added in ES6) : 배열 형태의 매개 변수
function printAll (...args) {
  for (let i=0; i<args.length; i++) {
    console.log(args[i]);
  }
  // 간단한 형태
  for (const arg of args) {
    console.log(arg);
  }
}
printAll('dream', 'grace', 'lala'); // 길이가 3인 배열 형태로 전달


// 5. Local Scope
let globalVar = 'global';

function printMessage() {
  let localVar = 'local';
  console.log(localVar);
  console.log(globalVar);

  function printAnother() {
    console.log(localVar);
    let childMessage = 'childMessage';
  }
  // console.log(childMessage); // not defined
}

printMessage();


// 6. Return a value
// 기본: return undefined
function sum (a, b) {
  return a + b;
}
const result = sum(1, 2);
console.log(`sum: ${result}`);


// 7. Early return, Early exit
// bad
function upgradeUser(user) {
  if (user.point > 10) {
    // long upgrade logic
  }
}

// good
function upgradeUser(user) {
  if(user.point <= 10) { // 조건이 맞지 않는 경우 빨리 return
    return;
  }
  // long upgrade logic
}



// First-class Function

// 1. Function Expression
// - 선언하기 전에 호출 가능 (hoisting)
const print = function() { // Anonymous function -> 변수에 할당
  console.log('print 함수 호출');
};
print();
const printAgain = print;
printAgain();
const sumAgain = sum;
console.log(sumAgain(1,3));

// 2. Callback function using function expression
function randQuiz(answer, printYes, printNo) {
  if (answer === 'love you') {
    printYes();
  } else {
    printNo();
  }
}

const printYes = function() {
  console.log('yes!');
};

const printNo = function no() { // Named Function
  console.log('no!');
};

randQuiz('wrong', printYes, printNo);
randQuiz('love you', printYes, printNo);

// Arrow function (항상 anonymous)
const e = function () {
  console.log('simplePrint');
};

const simplePrint = () => console.log('simplePrint');
const add = (a, b) => a + b;
const simpleMultiply = (a, b) => {
  return a * b;
};

// IIFE (선언하면 바로 실행되는 함수)
(function hello() {
  console.log('IIFE');
})();

```
