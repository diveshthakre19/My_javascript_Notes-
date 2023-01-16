# Hoisting

Hoisting is mechanism in javascript where functions and variables declaration are moved to the top of the scope even before the code starts execution.
This means no matter where the variables and functions are declared, thay are moved to the top of their scope
regardless of there scopes are global or local.

## Variable Hoisting

in js, an undedlared variable is assinged the value undefined at execution and also type of undefined

- refrence error is thrown when trying to access a previously undeclared variable

```javascript
console.log(name);
// Refrence Error: name is not defined
```

- key thing to note in regards to hoisting is that only thing that move upwards is variable declarition, not the actual value given to the variable.

```javascript
console.log(test); // undefined
var test = "someThing";
```

Examples:

```javascript
var something;
console.log(age); // undefined
something = "variabele has been hoisted ";
```

```javascript
var hoist(){
    var message
    console.log(message)
    message= "it is simple"
}
hoist() // undefined
```

### Only variables are Hoisted

Javascript only hoist declaration, not initialzation. if a variable is declared is declared and initilized after using it, the value will be undefined

for example

```javascript
console.log(num); // undefined

var num;

num = 6;
```

To avoid the pitfall, we woud make sure to declare and initilize the variables before we use it.

```javascript
function hoist() {
  var message = "Hoisting is cool";

  return message;
}

hoist(); // hoisting is cool
```

The variable declaration, var message whose scope is the function hoist( ), is hoisted to the top of the function.

Newer versions of js is trying to get away from this way of writing code.

it is good to know that hoisting exists, but you shoud never actually use it. Always declare variables excatly where they shoud be at the top of the scope they're used in. That way, your code is always going to be predictable, and you don't have to rely on hoisting.

Let and const hoist but you cannot access them before the acyual declaration is eveluated at runtime. Ehat dose this mean? Let's see it in a simle example:

```javascript
console.log(itsVarString); // undefined
var itsVarString = "var";

console.log(itsLetString); // RefrenceError
let itsLetString = "let";

console.log(itsConstString); // RefrenceError
const itsConstString = "const";
```

with let and const you gat back excatly what you woud expect: a refrence error. And that's good. Thats javaScripts's way of letting us know that we need to write clean code.

- you shoud always declare variable before using them, it's common sense.

### Functional Hoisting

The same var variables, the function declaration are hoisted comletly to the top.

```javascript
hoisted(); // This function has been hoisted.

function hoisted() {
  console.log("This function has been hoisted.");
}
```

Again, woud youever need to do this? No.
Always declare the function before you call it.

### Function Expression

Another great thing, is that constants and functions expression save us from doing that. Function expression (the more modern way of writing functions, with const keyword) are not hoisted.

```javascript
functionExpression(); // RefrenceError
const functionExpression = () => {
  console.log("Will this work?");
};
```

hoisting, as well as closures, Which we're going to see next, are complex topics. i woud say that they are not all that use full in everyday coding.
