## Variable and Data types

variables are like a like a Box Where we can store values.

## Rules for choosing variables

- Letters, Digits, UnderScores and $ sing allowed
- Must begin with $, \_ or a letter
- js Reserved key words cannot be used as a variable name
- javascript is case sensitive language so be aware.

## const, let and var

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
for (statement1; statemant2; statement3) {
  // run this code
}

for (let i = 0; i <= 10; i++) {
  console.log(i);
}
```

- statement 1 is executed one time.
- statemat 2 is the condition on which loop continues to run.
- statement 3 is executed every time loop body is executed.

## 7) While Loop

> while loop will exicute the code as long as the given condition evaluates true .

```javascript
let i = 0;
while (i < 12) {
  // run this code
  i++;
}
```

---

## 8) Do While Loop

> while loop will run as long as the given condition evaluates true. but, unlike previous types it will first run the code and then evaluates the code, so even if the condition is false it will run **_atleast one time_**, it has its own use cases.

```javascript
let i = 5;
{
  // run this code
  while (i < 4) i++;
}
```

- Also there are two types of loops **_for loop_** & **_for in_** loop we will learn about them in future.

---

## 9) Functions

> Function is like a mini program where we can perform some specific task based on the code written inside it's block and arguments passed.

- syntax

```javascript
 function fnSampel=(x,z){
  // code which will run when someone call this function.
  console.log(x-z)
 }
 fnSampel(50,3) // function invocation
```

function invacation is the way to use the code written inside the function.

- functions also can return the value to the value which will go inside the caller.

```javascript
 function sum=(a,b,c){
  let ans = (a+b+c)
   return ans;
 }

 let myAnswer = sum(5,9,1)
 console.log(myAnswer) // 15

```
