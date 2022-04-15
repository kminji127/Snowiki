# Variable

```javascript
// 2. Variable, rw(read/write)
// let (Added in ES6)
let globalName = 'global name';
{
  let name = 'snow';
  console.log(name);
  name = 'hello';
  console.log(name);
}
console.log(name);
console.log(globalName);


// 3. Constant, r(read only)
const daysInWeek = 7;
const maxNumber = 5;


// 4. Variable types
// 원시 타입 primitive type (값 자체 value가 메모리에 저장)
// 객체 타입 object type (값을 가리키는 참조 reference를 메모리에 저장)

// number
const count = 17; // integer
const size = 17.1; // decimal number
console.log(`value: ${count}, type: ${typeof count}`);
console.log(`value: ${size}, type: ${typeof size}`);

// number - special numeric values
const infinity = 1 / 0;
const negaviteInfinity = -1 / 0;
const NA = 'not a number' / 2;
console.log(infinity);
console.log(negaviteInfinity);
console.log(NA); // NaN

// string
const char = 'c';
const brendan = 'brendan';
const greeting = 'hello' + brendan;
console.log(`value: ${greeting}, type: ${typeof greeting}`);
const helloBob = `hi ${brendan}!`; // template literals (string)
console.log(`value: ${helloBob}, type: ${typeof helloBob}`);

// boolean
// false: 0, null, undefined, NaN, ''
// true: any other value
const canRead = true;
const test = 3 < 1; // false
console.log(`value: ${canRead}, type: ${typeof canRead}`);
console.log(`value: ${test}, type: ${typeof test}`);

// null
let nothing = null;
console.log(`value: ${nothing}, type: ${typeof nothing}`);

// undefined
let x;
//let x = undefined;
console.log(`value: ${x}, type: ${typeof x}`);

// symbol
// create unique identifiers for objects (객체마다 고유한 식별자)
const symbol1 = Symbol('id');
const symbol2 = Symbol('id');
console.log(symbol1 === symbol2); // false
console.log(`value: ${symbol1.description}, type: ${typeof symbol1}`);

// object
const mj = {name:'mj', age:21};
mj.age = 22; // 변경 가능
console.log(`name: ${mj.name}, age: ${mj.age}`);


// 5. Dynamic typing
let text = 'hello';
console.log(text.charAt(0));
console.log(`value: ${text}, type: ${typeof text}`);

text = 1;
console.log(`value: ${text}, type: ${typeof text}`);

text = '7' + 5;
console.log(`value: ${text}, type: ${typeof text}`);

text = '8' / '2';
console.log(`value: ${text}, type: ${typeof text}`);

```
