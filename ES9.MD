## The specifications of ECMAScript language 2018 (es9)

### Object rest properties
Rest properties for object destructuring assignment.
```JavaScript
let { fname, lname, ...rest } = { fname: "Hemanth", lname: "HM", location: "Earth", type: "Human" };
fname; //"Hemanth"
lname; //"HM"
rest; // {location: "Earth", type: "Human"}
```

### Object spread properties
Spread properties for object destructuring assignment.
```JavaScript
let info = {fname, lname, ...rest};

info; // { fname: "Hemanth", lname: "HM", location: "Earth", type: "Human" }
```

### Promise prototype finally
Promise API is extended by an optional finally block which is called in any case (after the Promise is resolved or is rejected).
```JavaScript
function testFinally() {
  return new Promise((resolve,reject) => resolve())
}

testFinally().then(() => console.debug("resolved")).finally(() => console.debug("finally"))
// resolved
// finally
```