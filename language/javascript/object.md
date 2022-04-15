# Object

```javascript
// Object
// - Key와 Value의 집합체인 프로퍼티의 집합
// - {key : value};

// 1. 리터럴, 프로퍼티
const etoile = {name: 'etoile', age: 21}; // object literal
const obj = new Object(); // object constructor

function print(person) {
  console.log(person.name);
  console.log(person.age);
}

print(etoile);

// 프로퍼티 나중에 추가 가능
etoile.hasJob = false;
console.log(etoile.hasJob);

// 프로퍼티 나중에 삭제 가능
delete etoile.hasJob;
console.log(etoile.hasJob); // undefined


// 2. Computed properties
// key는 string 타입으로 지정해서 받아와야 함
console.log(etoile.name);
console.log(etoile['name']);
etoile['hasJob'] = true;
console.log(etoile.hasJob); // true

function printValue(obj, key) {
  console.log(obj[key]);
}
printValue(etoile, 'name');
printValue(etoile, 'age');


// 3. Property value shorthand
const person1 = {name: 'bob', age: 20};
const person2 = {name: 'steve', age: 23};
const person3 = {name: 'dave', age: 19};
const person4 = new Person('elile', 30);
console.log(person4);


// 4. Constructor function 생성자 함수
function Person(name, age) { // Object 생성 함수
  this.name = name;
  this.age = age;
  // return this;
}


// 5. in operator: key 유무
console.log('name' in etoile); // t
console.log('random' in etoile); // f
console.log(etoile.random); // undefined


// 6. for..in vs for..of
console.clear();
for (const key in etoile) {
  console.log(key);
}

const array = [1, 2, 4, 5];
for (const value of array) {
  console.log(value);
}
```
