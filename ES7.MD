## The specifications of ECMAScript language 2016 (es7)

### Includes

 basic example

```JavaScript
[1, 2, 3].includes(-1)                   // false
[1, 2, 3].includes(1)                    // true
[1, 2, 3].includes(3, 4)                 // false
[1, 2, 3].includes(3, 3)                 // false
[1, 2, NaN].includes(NaN)                // true
['foo', 'bar', 'quux'].includes('foo')   // true

```

if fromIndex is greater than or equal to the len of array,
 false is automatically returned

```JavaScript
let arr = ['x', 'y', 'z'];

arr.includes('x', 2)    // false
arr.includes('z', 10)  // false
```

### Exponentiation
basic example

```JavaScript
Math.pow(5, 2)
 // same
5 ** 2
// 5 ** 2 === 5 * 5
```