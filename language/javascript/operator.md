# Operator

```javascript
// 1. String concatenation
console.log('my' + ' cat');
console.log('1' + 2); // 12
console.log(`string litersals: 1 + 2 = ${1+2}`);
console.log('sm\'s book');


// 2. Numeric operators
console.log(1 + 1);
console.log(1 - 1);
console.log(1 / 2);
console.log(1 * 2);
console.log(18 % 5); // 나머지
console.log(2 ** 3); // 제곱


// 3. Increment, Decrement operators
let counter = 2;
const preIncrement = ++counter;
// counter = counter + 1;
// preIncrement = counter;
console.log(`preIncrement: ${preIncrement}, counter: ${counter}`); // 3, 3

counter = 2;
const postIncrement = counter++;
// postIncrement = counter;
// counter = counter + 1;
console.log(`postIncrement: ${postIncrement}, counter: ${counter}`); // 2, 3

counter = 2;
const preDecrement = --counter;
console.log(`preDecrement: ${preDecrement}, counter: ${counter}`); // 1, 1

counter = 2;
const postDecrement = counter--;
console.log(`postDecrement: ${postDecrement}, counter: ${counter}`); // 2, 1


// 4. 할당 연산자
let x = 3;
let y = 6;
x += y; // x = x+y;
console.log(`x = ${x}`);


// 5. 비교 연산자
console.log(10 < 4); // false
console.log(10 <= 4); // false
console.log(10 > 4); // true
console.log(10 >= 4); // true


// 6. 논리 연산자
const value1 = true;
const value2 = 4 < 2; // false

// ||(or)
// 처음 true가 나온 순간 멈춤 -> 간단한 value를 먼저 호출
console.log(`or: ${value1 || value2 || check()}`); // true

// &&(and)
// 처음 false가 나온 순간 멈춤 -> 간단한 value를 먼저 호출
console.log(`and: ${value1 && value2 && check()}`);

  // null 체크: nullableObject && nullableObject.something
  // if (nullableObject != null) {
  //   nullableObject.something;
  // }

function check() { // true
  for (let i=0; i<10; i++) {
    //wasting time
    console.log('😱');
  }
  return true;
}

// !(not)
console.log(!value1);


// 7. Equality
const stringFive = '5';
const numberFive = 5;

// == : loose equality (타입 달라도 내용 같으면 true)
console.log(stringFive == numberFive); // true
console.log(stringFive != numberFive);

// === : strict equality (타입 다르면 false)
console.log(stringFive === numberFive); // false
console.log(stringFive !== numberFive);

// object equality by reference
// 객체의 메모리 참조 값은 각기 다르다
const mj1 = {name: 'mj'};
const mj2 = {name: 'mj'};
const mj3 = mj1;
console.log(mj1 == mj2); // false
console.log(mj1 === mj2); // false
console.log(mj1 === mj3); // true

console.log(0 == false); // t
console.log(0 === false); // f
console.log('' == false); // t
console.log('' === false); // f
console.log(null == undefined); // t
console.log(null === undefined); // f


// 8. 조건 연산자
// if, else if, else
const user = 'grace';
if (user === 'grace') {
  console.log('Welcome, Grace!');
} else if (user === 'coder') {
  console.log('Amazing Coder');
} else {
  console.log('unknown');
}


// 9. Ternary operater
// 조건 ? value1 : value2;
// true면 왼쪽, false면 오른쪽 실행
console.log(user === 'grace' ? 'yes' : 'no');


// 10. Switch문
const browser = 'IE';
switch (browser) {
  case 'IE':
    console.log('go away!');
    break;
  case 'Chrome':
  case 'Firefox':
    console.log('love you!');
    break;
  default:
    console.log('same all!');
    break;
}


// 11. 반복문
let i = 3;
while (i > 0) {
  console.log(`while: ${i}`);
  i--;
}

// 실행한 다음에 조건 검사
do {
  console.log(`do while: ${i}`);
  i--;
} while (i > 0);


// 12. for문 : for(시작문; 조건문; step)
for (i=3; i>0; i--) {
  console.log(`for: ${i}`);
}

// inline variable declaration
for (let i=3; i>0; i=i-2) {
  console.log(`inline variable for: ${i}`);
}

// nested loops
for (let i=0; i<10; i++){
  for (let j=0; j<10; j++){
    console.log(`i:${i}, j:${j}`);
  }
}


// break, continue
for (let i=0; i<11; i++) {
  if(i % 2 !== 0) {
    continue;
  }
  console.log(`q1. ${i}`);
}

for (let i=0; i<11; i++) {
  if (i > 8) {
    break;
  }
  console.log(`q2. ${i}`);
}
```
