# JavaScript "Best" Practices

### Use `const` instead of anything
```js
var one = 1 // Bad
let one = 1 // Also bad
const one = 1 // Good!
```
If you need a variable — just use object instead of immutable types
```js
const variableHash = {variable:1}
variableHash.variable = 2
variableHash // Properties of const are mutable! {variable:2}
```

### Always use lowercase name of "variables"
```js
const MAX_LENGTH = 1 // Bad
const maxLength = 1 // Good!
```

### Never put the semicolons to the end of a line
It will be still valid JavaScript
```js
const a = 1; // Bad
const a = 1 // Good!
```

### Write less code as much as possible
```js
const maxLength = 1 // Bad
const mL=1 // Good!
```

### Indentations are the hard work!
You can write less code by rejection of any type of indentation.
```js
function a() { //
  return 1     // Obviously bad
}              //

function a(){ //
return 1      // Good!
}             //
```
Or, in very rare case is acceptable to use semicolons as intentations. In this case, use 3 semicolons.
```js
function a() { //
;;;return 1    // Ok
}              //
```

### Functions are abandoned now
```js
function a(x){return x} // Bad
a=x=>x // Good
```
If you need a function that has no return value or it  — simply use curly braces syntax:
```js
a=x=>{} // Good

a=x=>{   //
return x // Good
}        //
```
