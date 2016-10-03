# JavaScript "Best" Practices
![hipsterlogogenerator_1475488442538](https://cloud.githubusercontent.com/assets/584632/19034058/c5c2462a-898b-11e6-84b7-3cb5657e2e3d.png)

## The main ideas
1. Write less to save your time to be more productive.
2. Write at least valid ES6 code. Valid means good enough.
3. Write robust, unified code that should be ready for any kind of refactoring.
4. Avoid any side effects. Any!

### Use `const` instead of anything
```js
var one = 1 // Bad
let one = 1 // Also bad
const one = 1 // Good!
```
If you need a variable — just use object instead of immutable types. Don't worry, `const` doesn't make something immutable — you just can not override the value.
```js
const variableHash = {variable:1}
variableHash.variable = 2
variableHash // {variable:2} Properties of const are still mutable!
```

### Always use lowercase name of "variables"
As you may know, `const` doesn't mean that the variable is constant. It means only intent of not changing the variable. Since they are not constants, you don't need to follow weird code conventions from retarded languages.
```js
const MAX_LENGTH = 1 // Bad
const maxLength = 1 // Good!
```

### Never put the semicolons to the end of a line
It will be still valid JavaScript. Valid means good.
```js
const a = 1; // Bad
const a = 1 // Good!
```

### Shorten your "variables" names
```js
const maxLength = 1 // Bad
const mL=1 // Good!
```

### Indentations is a hard work!
You can write less code by rejection of any type of indentation.
```js
function a() { //
  return 1     // Obviously bad
}              //

function a(){ //
return 1      // Good!
}             //
```
Or, in very rare case is acceptable to use the semicolons as intentations.  
In this case, use 3 semicolons.
```js
function a(){ //
;;;return 1    // Ok
}              //
```

### Avoid semicolons elsewhere
There is no reason to use semicolons at all.

### Avoid `for` loops
`for` loops are using semicolons on their syntax. Replace them by array's methods or as a last resort `while`
```js
const v={i:0}
for(;v.i<10;v.i++) // Bad

[...Array(10).keys()].forEach(i=>i) // Good

const v={i:0}
while(v.i<10)v.i++ // Ok
```

### The `function` word is abandoned now
Never use it again!
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
If you need to return an object — use parentheses syntax:
```js
a=x=>{a:1} // Will not work as expected

a=x=>({a:1}) // Great!
```


# Contributing
Please feel free to extend this list of new "best" practices in JavaScript.  
Pull Requests are welcomed!
