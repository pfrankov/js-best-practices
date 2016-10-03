<h1 align="center">
  <img src="https://cloud.githubusercontent.com/assets/584632/19035533/2f877488-8994-11e6-873c-863e18a4398a.png" alt="JavaScript 'Best' Practices" width="250">
  <br>
  JavaScript "Best" Practices
  <br>
  <br>
</h1>

### The main ideas
1. Write less characters to save your time and to be more productive.
2. Write at least valid ES6 code. Valid means good enough.
3. Write robust, unified code that should be ready for any kind of refactoring.
4. Avoid any side effects. Any!
5. `undefined` is not a function!

#### Use `const` instead of anything
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
You think that it is uncomfortable? Yes, and it should be!  
Less variables means less side effects means much robust code.

#### Use as less `const` word as you can
```js
const a=1 //
const b=2 // Bad. 29 chars
const c=3 //

const a=1,b=2,c=3 // Good. 17 chars. Almost ×2 speed up
```

#### Always use lowercase name of "variables"
As you may know, `const` doesn't mean that the variable is constant. It means only intent of not changing the variable. Since they are not constants, you don't need to follow weird code conventions from retarded languages.
```js
const MAX_LENGTH = 1 // Bad
const maxLength = 1 // Good!
```

#### Never put the semicolons to the end of a line
It will be still valid JavaScript. Valid means good.
```js
const a = 1; // Bad
const a = 1 // Good!
```

#### Shorten your "variables" names
```js
const maxLength = 1 // Bad. 19 chars. 20 keystrokes (Shift for "L")
const mL=1 // Ok. 11 keystrokes.
const ml=1 // Good. 10 keystrokes. Twice less than in the first example.
```

#### Indentations is a hard work!
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
In this case, use 3 semicolons. It's a standard for such things.
```js
function a(){ //
;;;return 1    // Ok
}              //
```

#### Avoid semicolons elsewhere
There is no reason to use semicolons at all.

#### Avoid `for` loops
`for` loops are using semicolons on their syntax. Replace them by array's methods or `while` as a last resort
```js
for(const v={i:0};v.i<10;v.i++) // Bad

const v={i:0}
while(v.i<10)v.i++ // Ok

[...Array(10).keys()].forEach(i=>i) // Good
```

#### The `function` word is abandoned now
Never use it again!
```js
function a(x){return x} // Bad
a=x=>x // Good
```
If you need a function that has no return value or it should be multiline — simply use curly braces syntax:
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

// But!
a=x=>({  //
return x // Will not work. JS thinks that we have a deal with an object
})       //
```


## Contributing
Please feel free to extend this list of new "best" practices in JavaScript.  
Pull Requests are welcomed!
