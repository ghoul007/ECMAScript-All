## The specifications of ECMAScript language 2017 (es8)

### async function
The AsyncFunction constructor creates a new async function object. In JavaScript every asynchronous function is actually an AsyncFunction object
```JavaScript
const resolveAfter3Seconds = function() {
  console.log('starting 3 second promsise')
  return new Promise(resolve => {
    setTimeout(function() {
      resolve(3)
      console.log('done in 3 seconds')
    }, 3000)
  })
}

const resolveAfter1Second = function() {
  console.log('starting 1 second promise')
  return new Promise(resolve => {
      setTimeout(function() {
        resolve(1)
        console.log('done, in 1 second')
      }, 1000)
  })
}

const sequentialStart = async function() {
  console.log('***SEQUENTIAL START***')
  const one = await resolveAfter1Second()
  const three = await resolveAfter3Seconds()

  console.log(one)
  console.log(three)
}

sequentialStart() // invoke async function
```

### Object.entries
Object.entries gives us the ability to get an object's enurmerable property pairs by returning an array of any given object's own eumberable properties. /ie: [key, value] pairs. Note that the order is the same as provided by the for...in loop.

```JavaScript
const obj = { self: 'that', norf: 'quux' }
console.log(Object.entries(obj))

// => [ ['self', 'that'], ['norf', 'quux'] ]
```

```JavaScript
const obj = { 50: 'a', 1: 'b', 5: 'c' }
console.log(Object.entries(obj))

// => [ ['1', 'b'], ['5', 'c'], ['50', 'a'] ]
```

### Object.value

return an array of a given object's own enumerable property values.

```JavaScript
const obj = { a: 100, b: 200 }
console.log(Object.values(obj))

// => [100, 200]
```


### Object.getOwnPropertyDescriptors()
Object.getOwnPropertyDescriptors() returns all own property descriptors of a given object. A property descriptor is a record with one of the following attributes:

value, writable, get, set, configurable, enumerable

```JavaScript
let myObj = {
  property1: 'foo',
  property2: 'bar',
  property3: 42,
  property4: () => console.log('prop4')
}

Object.getOwnPropertyDescriptors(myObj)

/*
{ property1: {…}, property2: {…}, property3: {…}, property4: {…} }
  property1: {value: "foo", writable: true, enumerable: true, configurable: true}
  property2: {value: "bar", writable: true, enumerable: true, configurable: true}
  property3: {value: 42, writable: true, enumerable: true, configurable: true}
  property4: {value: ƒ, writable: true, enumerable: true, configurable: true}
  __proto__: Object
*/
```

### Trailing Commas
 in array
 ```JavaScript
 let arr = [
  10,
  20,
  30,
  40,
  50,
]

arr // [10, 20, 30, 40,  50]
arr.length // 5
```

in object
```JavaScript
const obj = {
  trailing: 'comma',
  is: 'allowed',
  in: 'JavaScript..',
}
```