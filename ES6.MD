## The specifications of ECMAScript language 2015

### Arrow Function
Arrow is a function using this ```=>``` syntax
```JavaScript
const add = (a, b) => a + b

```
[see more](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)


### Classes
Classes support prototype-based inheritance, instance and static methods and constructors
```JavaScript
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
}
```
[see more](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)


### Template Strings
You can use multi-line strings and string interpolation features
```JavaScript
// Basic literal string creation
`In JavaScript '\n' is a line-feed.`

// Multiline strings
`In JavaScript this is
 not legal.`

// String interpolation
var name = "Bob", time = "today";
`Hello ${name}, how are you ${time}?`
```
[see more](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)


### Destructuring
makes it possible to unpack values from arrays, or properties from objects
```JavaScript
// list matching
var [a, , b] = [1,2,3];

// object matching
var { name: a, address: { code: b }} = {name: 'ahmed', address:{code: 6000}}


// Can be used in parameter position
function g({name: x}) {
  console.log(x);
}
g({name: 5})
```
[see more](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

### Default
allow named parameters to be initialized with default values
```Javascript
function f(x, y=1) {
  return x + y;
}
f(3) == 4
```
[see more](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)




### Rest
allows us to represent an indefinite number of arguments as an
```Javascript
function f(x, ...y) {
  return x * y.length;
}
f(3, "hello", true) == 6
```
[see more](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters)




###  Spread
 allows an iterable to expand in places where 0+ arguments are expected
```Javascript
function f(x, y, z) {
  return x + y + z;
}
// Pass each elem of array as argument
f(...[1,2,3]) == 6
```
[see more](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)

### Let & const
Block-scoped binding constructs. let is the new var. const is single-assignment. Static restrictions prevent use before assignment.

```JavaScript
function f() {
  {
    let x;
    {
      // okay, block scoped name
      const x = "sneaky";
      // error, const
      x = "foo";
    }
    // error, already declared in block
    let x = "inner";
  }
}
```
[let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let), [const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)


### For..Of
creates a loop iterating
```JavaScript
for (let o of foo()) {
  console.log(o);
  // expected output: 1

  break; // closes iterator, triggers return
}
```
[see more](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)

### Module

```JavaScript
// math.js
export function add(x, y) {
  return x + y;
}
export var pi = 3.141593;
```

```JavaScript
// test.js
import {sum, pi} from "math";
cont result = sum(pi, 5);
```
[import](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import), [export](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export)

### Map + Set + WeakMap + WeakSet
 data structures
```JavaScript
// Sets
var s = new Set();
s.add("hello").add("ahmed");
s.size === 2;
s.has("ahmed") === true;

// Maps
var m = new Map();
m.set("hello", 42);
m.set(s, 34);
m.get(s) == 34;

// Weak Maps
var wm = new WeakMap();
wm.set(s, { extra: 42 });


// Weak Sets
var ws = new WeakSet();
ws.add({ data: 42 });

```
[Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map),
[Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set),
[WeakMap](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap),
[WeakSet](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet)


### Math + Number + String + Array
Many new library additions, including core Math libraries, Array conversion helpers, String helpers, and Object.assign for copying.

```JavaScript
Number.EPSILON
Number.isInteger(Infinity) // false
Number.isNaN("NaN") // false

Math.acosh(3) // 1.762747174039086
Math.hypot(3, 4) // 5
Math.imul(Math.pow(2, 32) - 1, Math.pow(2, 32) - 2) // 2

"abcde".includes("cd") // true
"abc".repeat(3) // "abcabcabc"

Array.from(document.querySelectorAll('*')) // Returns a real Array
Array.of(1, 2, 3) // Similar to new Array(...), but without special one-arg behavior
[0, 0, 0].fill(7, 1) // [0,7,7]
[1, 2, 3].find(x => x == 3) // 3
[1, 2, 3].findIndex(x => x == 2) // 1
[1, 2, 3, 4, 5].copyWithin(3, 0) // [1, 2, 3, 1, 2]
["a", "b", "c"].entries() // iterator [0, "a"], [1,"b"], [2,"c"]
["a", "b", "c"].keys() // iterator 0, 1, 2
["a", "b", "c"].values() // iterator "a", "b", "c"

Object.assign(Point, { origin: new Point(0,0) })
```
[Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number),
[Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math),
[Array.from](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from),
[Array.of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/of),
[CopyWithin](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/copyWithin),
[Object.assign](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/assign)

### Binary and Octal Literals
Two new numeric literal forms are added for binary (b) and octal (o).
``` JavaScript
0b111110111 === 503 // true
0o767 === 503 // true
```