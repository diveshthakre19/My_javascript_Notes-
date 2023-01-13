# scope in javascript

Scopes simply allow us to know where we have access to our variables.
it shows us the accessability of our variables,functions and objects in some particular part of code.

you may ask why woud we want to limit the visibility of variables and not have everything avaliable everywhere in our code?
Firstly it privides us with some level of security, it helps to improve efficiency track bugs and reduce them. it also solves the problem of naming variables.

### javascript have three types of scopes

### global Scope, Local scope and Block scope (only with let and const)

variables define inside a function are in local scope while variables define outside of a function are global scope. Each function When invoked creates a new scope

There are rules about how scope works, but usually you can search for the closest { }
braces around where you define the variable. That 'block' of code is its scope.

## global Scope

When you start writing in a javascript document, you're in the Global scope.

variables written inside the Global scope can be accessed by any other scope in the whole js file

```javascript
const Username = "Divesh";

const printName = () => {
  console.log(Username);
};

printName(); // "Divesh"
```

### Advantages of using Global Variable.

- You can access the global variable from all the function of modules in the program.

- it is idealy used to storing "constants" it helps you keep the consistency.

- A Global variable is useful When multiple functions are accessing the same data.

### Disadvantages of using Global Variable.

- Too many variables declared as global, then they remain in the memory till program execution is completed. This can cause Out of Memory issue.

- Data can be modified by any function. Any statement written in the program can change the value of the global variable . This may give unpredictable results in multi-tasking environments

- if global variables are discontinued due to code refactoring, you will need to change all the modules where they are called.

## Local Scope

Variable defined inside a function are in the local scope.

```javascript
// Global scope
const func1 = () => {
  // local scope #1

  const func2 = () => {
    // local scope #2
  };
};
```

### Advantages of using Local Variables.

- The use of local variables offer a guarantee that the values of variable swill remain intact while the task is running.

- They are deleted as soon as any function is over and released the memory space which it occupies

- You can give local variables the same name in the diffrent function because they are only recognized by the function they are declared in.

### Disadvantages of using Local Variables.

- They have a very limited scope.
  This isn't necessarily a disadvantage, but if you ever find yourself needing to use thet variable in a parent scope, just declare it there. Let me show you what is mean.

if you need to use a variable only inside the
func2 function, just declare it there.

```javascript
// Global scope
const func1 = () => {
  // local scope #1

  const func2 = () => {
    // local scope #2
  };
};
```

if for some reason, you need to use it booth in the func1 and func2 functions, declare it in the func1
And if you need to use it everywhere across the file, declare it in the globar scope.

## Block Scope

Block statements like if or for and While loops, unlike functions, don't create a new scope.
Variable defined inside of a block statement will remain in the scope they were already in.

```javascript
if (true) {
  // this 'if' condition block dosen't create a new scope
  var name = "Divesh"; // name is still in the global scope
}

console.log(name); // 'Divesh'
```

That is only true with var.
variables defined with const or let have something called Block Scope. that means that they will be avaliable only inside the block of code you create them in.

```javascript
if (true) {
  // this 'if' condition block dosen't create a new scope

  // name is in the global scope because of the 'var' keyword
  var name = "Divesh";
  // age is in the local scope because of the 'let' keyword
  let age = 19;
  // skills in the local scope because of the 'const' keyword
  const skills = "Javascript and React js ";
}

console.log(name); // 'Divesh'
console.log(age); // Uncaught RefrenceError: age is not defined
console.log(skills); // Uncaught RefrenceError: skills is not defined
```

if a variabe or other expression is not "in the current scope", then it is unavaliabe for use.

The local and global variables are equally important while writing a program in any programing language

however, a large number of global variable may occupy a huge memory.

an undesirable change to global variables is become tough to identify. Therefore, it is advisible to avoid declaring unwanted global variables. Always declare in the scope that you want to use them in.

### Key Diffrences

- Local variables is declared inside a function where as global variable is declared outside the function.

- local variable are stored on the stack whereas the Global variables are stored on a fixed location decided by the compiler

- Local variables dosen't provide data sharing whereas Global variables provides data sharing.

- Local variable are created when the function has started execution and lost when the function terminates, on the other hand, global variable is created as execution starts and is lost when the program ends.

- parameters passing is required for local variables whereas it is not necessary for a global variable.

---
