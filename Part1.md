# Variable and Data types

variables are like a like a Box Where we can store values.

# Rules for choosing variables

- Letters, Digits, UnderScores and $ sing allowed
- Must begin with $, \_ or a letter
- js Reserved key words cannot be used as a variable name
- js is case sensitive language so be aware

# const, let and var

## var vs let in Javascript

- var is globaly Scoped while let and const are block scoped.
- Block scope: A variable when declared inside the if or switch conditions or inside for or while loop, are accessible within that particular condition or loop.

* To be consise the variable declared inside the curly braces are called within block scope

- var can be updated and redeclared within its Scope.
- let can be updated but not redeclared.
- var variable are initalized with undefined where as let and const variables are not inatilized
- const must be inatilized during declarition unlike let and var.

```javascript
let a = 85; // this a contains 85
a = "Eighty seven";
console.log(a); // "Eighty seven"

// let 4divesh = "this is not allowed"
// --------------------------------------------
```

## 3) Primitive and object

- primitive Data types are a set of basic data type in js.
- Object is a non primitive datatype in js.
- 7 types of primitive datatype are Null, Number, string, symbol, Boolean, Bigint & Undefined

### Primitive Data Type

```javascript
let type1 = null;
let type2 = 56;
let type3 = Symbol("this is a symbol");
let type4 = "string";
let type5 = true;
let type6 = BigInt("665");
let type7 = undefined;
console.log(typeof type1, type2);
```

// ----------------------------------------------

## Object

```javascript
const obj1 = {
  FirstName: "divesh",
  lastName: "thakre",
  passion: "learning",
  isAwesone: true,
};
console.log(obj1.FirstName);
console.log(obj1["passion"]);
```

## 4) Operators and Expressions

## 5) Conditionals

- some times we have to execute some code based on certain condition for example a prompt might ask fro the categeory so according to the categeory ehich user has inserted we have to execute special code

```javascript
// so javascript gives us three format of statements
// 1) if statemant
let condition = true;
if (condition) {
  // do this
}
condition = false;
// 2) if else statement
if (condition) {
  // do this
} else {
  // do this
}
// 3) if .... else if .... else
if ("condition is true") {
  ("execute this code ");
} else if ("condition is true") {
  ("execute this code ");
}

// Ternary Operator
condition
  ? console.log("condition is true")
  : console.log("condition is false");
```

## 6) For Loop

- We use loops to perform repeated actions
- for loops a block of code x no. of times

```javascript
for (let i = 0; i <= 10; i++) {
  // this code will exicute 10 times
}
```

- statement 1 is executed one time
- statemat 2 is the condition on which loop continues to run.
- statement 3 is executed every time loop body is executed
