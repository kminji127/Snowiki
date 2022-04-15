# Class

```javascript
// class: template (붕어빵틀)
// object: Instance of a class (팥붕어빵, 크림붕어빵..)

// 1. 클래스 선언
class Person {

  // 생성자(constructor)
  constructor(name, age) {
    // fields
    this.name = name;
    this.age = age;
  }

  // 메소드(method)
  speak() {
    console.log(`${this.name}: hello!`);
  }
}

const mj = new Person('mj', 21);
console.log(`name: ${mj.name}, age: ${mj.age}`);
mj.speak();


// 2. Getter, Setter
class User {
  constructor(firstName, lastName, age) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age; //  getter, setter 호출
  }

  get age(){
    return this._age;
  }

  set age(value) {
    // if (value < 0) {
    //   throw Error('나이는 음수가 될 수 없습니다');
    // }
    this._age = value < 0 ? 0 : value;
  }
}
const user1 = new User('Steve', 'Jobs', -1);
console.log(user1.age);


// 3. Fields (public, private) (최근 도입)
class Experiment {
  publicField = 2;
  #privateField = 0; // 클래스 외부에서 접근 불가
}
const experiment = new Experiment();
console.log(experiment.publicField);
console.log(experiment.privateField); // undefined


// 4. Static Properties and methods (최근 도입)
// 객체와 상관 없이 동일하게 반복적으로 사용되는 메소드
class Article {
  static publisher = 'publisher';
  constructor(articleNumber) {
    this.articleNumber = articleNumber;
  }
  static printPublisher() {
    console.log(Article.publisher);
  }
}

const article1 = new Article(1);
const article2 = new Article(2);
// console.log(article1.publisher); // undefined
console.log(Article.publisher);
Article.printPublisher();


// 5. 상속, 다양성
// - 공통 요소가 있을 때
class Shape {
  constructor(width, height, color) {
    this.width = width;
    this.height = height;
    this.color = color;
  }

  draw() {
    console.log(`drawing ${this.color} color of`);
  }

  getArea() {
    return this.width * this.height;
  }
}

// Shape 클래스를 상속
class Rectangle extends Shape { }
class Triangle extends Shape {
  // 필요한 함수만 오버라이딩(재정의)
  draw() {
    super.draw(); // 부모 클래스의 메소드 호출
    console.log('▲');
  }
  getArea() {
    return (this.width * this.height) / 2;
  }
  toString() { // Object 클래스 오버라이딩
    return `Triangle color: ${this.color}`;
  }
}

const rectangle = new Rectangle(20, 20, 'blue');
rectangle.draw();
console.log(`넓이: ${rectangle.getArea()}`);
const triangle = new Triangle(10, 30, 'red');
triangle.draw();
console.log(`넓이: ${triangle.getArea()}`);


// 6. instanceOf : 클래스 확인
console.log(rectangle instanceof Rectangle); // t
console.log(triangle instanceof Rectangle); // f
console.log(triangle instanceof Triangle); // t
console.log(triangle instanceof Shape); // t
console.log(triangle instanceof Object); // t (JS의 모든 클래스는 Object 클래스를 상속)
console.log(triangle.toString());
```
