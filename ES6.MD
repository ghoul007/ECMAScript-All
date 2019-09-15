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

