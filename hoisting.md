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

The variable declaration, var message whose scope is the function hoist(), is hoisted to the top of the function.

Newer versions of js is trying to get away from this way of writing code.

it is good to know that hoisting exists, but you shoud never actually use it. Always declare variables excatly where they shoud be at the top of the scope they're used in. That way, your code is always going to be predictable, and you don't have to rely on hoisting.
