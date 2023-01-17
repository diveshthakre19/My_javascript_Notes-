```javascript
const outer = () => {
  const outerVar = "hello";

  const inner = () => {
    const innerVar = "hi!";
    console.log(innerVar, outerVar);
  };
  return inner;
};

const innerFn = outer();
innerFn();
```

Normally when you exit a function, all its variables "disapper". This is bacause nothing needs them anymore. But what if you declare a function inside a function?

Then the inner function coud still be called later, and read the variables of the outer function.

in practice, this is very useful! But for this to work, the outer function's variables need to "stick around" somewhere. So in this case, javascript takes care of "keeping the variables alive instead of 'forgetting' them as it woud usually do.This is called a "Closure".

In other Words, a closure gives you access to an outer function's scope from inner function. in javascript Closures are created every time a function is created, at function creation time.

```javascript
const init = () => {
  const hobby = "Learning how to focus"; // hobby is a local variable created by init
  const displayHobby = () => {
    // displayHobby() is the inner function, a closure
    console.log(hobby); // using variable declared in the parent function
  };
  displayHobby();
};
init();
```

init() create sa local variable called name and a function called displayHobby().

The displayHobby( ) function is an inner function that is defined inside init() and is only avaliable within the body of the init() function. Note taht the displayHobby( ) function has no local variables of its own.

However, since inner functions have access to the variables of outer functions, displayhobby( ) can access the variable name declared in the parent function, init( ).

run the code and notice that thelog statement within the displayHobby() function sucessfully displays the value of the name variable, which is declared in its parent function.

Nested functions have access to the variables declared in their outer scope.

```javascript
const init = () => {
  const hobby = "Learning how to focus"; // hobby is a local variable created by init

  const displayHobby = () => {
    // displayHobby() is the inner function, a closure
    console.log(hobby); // using variable declared in the parent function
  };
  return displayHobby;
};
var myfunc = init();
myfunc();
```

Running this code has exactly teh same affect as the previous example of the init() function above; What's the diffrence and intresting is that displayHobbby() inner function is returned from the outer function bedore being executed.

At first glance, it it may seem unintutive that this code still works. in some programing languagea, the local variable within the function exists only for the duration of that function's execution.
once init() has finished executing, you might expevt that the name variabe wil no longer be accessible, this is obviously not the case in javascript.

The reacon is that functions in javascript form closures. A Closure is the combination of a function ans the enviornment within which that function was declared.

This enviornment consist of any local varaibles that were in-scope at the time the closure was created, in this case, myFunc is a refrence to the instance of the function displayHobby created when init is run.

The instance of displayHobby maintains a refrence to its lexical enviornment, Within Which the variable name exists.

For this reason, When my Func is invoked, the variable name remains avaliable for use and browser console.logs it.
