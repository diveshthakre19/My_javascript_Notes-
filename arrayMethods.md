# Arrays in Details

In programing, quite we will need an ordered collection, where we have a 1st, 2nd, 3rd element an so on.

For example, we need that to store a list of something: users, items elements etc.
There exists a special data structure named Array, to stpre ordered collectios.

### Declaration

This ia how we declare an array - most important part here are the square barckets:

```javascript
const months = ["January", "February", "March", "April"];
```

Array elements are numbered, Starting with Zero.

We can get an elements by its number in square brackets:

```javascript
console.log(months[0]); // 'January'
```

We can replace an element:

```javaScript
months[2] = 'Not March':
console.log(months) // ['January', 'February', 'Not March', 'April']
```

...Or add a new one to the array:

```javascript
months[4] = "May";
console.log(months); // ['January', 'February', 'Not March', 'April', 'May']
```

The total count of the elements in the array is its length:

```javascript
console.log(months.length); // 5
```

Array can store elements of any type:

```javascript
const arr = [
  "Apple",
  { name: "Divesh" },
  true,
  20,
  function () {
    console.log("hello");
  },
];
```

you're going to find yourself needing to looop
throught all elements of an array. That's where the for loop we've learned comes in handy:

Aside from containing variables at indexes, an array contains a variety of premade functions with which you can manupulate it's data, like adding or removing elements at certain positions! Let's take a look at a few of the most basic ones right now.

arry.push(value)
The array.push( ) function adds a new element, containing the entered variables, to the end of the array.

Example:

```javascript
const months = ["January", "February", "March", "April"];
months.push("May");
console.log(months); //  ["January", "February", "March", "April", "May"];
```

There's one importaint thing that many experinced web developers don't know about array.push( ). What's it's the return value?
Many woud think that the return value of the push would be an array, now including the element we've pushed. let's test it out:

```javascript
let someThing = months.push("May");
console.log(someThing); // 5
```

The return value is 5. Hmmm, why 5 ? Think about it.

It turns out that the array.push( ) returns the length of the array when the element is pushed.
We can even store it in a variable:

---

### **array.pop( )**

The array.pop( ) function on the oyher hand, dose quite the opposite, deleting the last element of an array.

```javascript
const names = ["divesh", "mahesh", "jayesh", "sudesh"];
names.pop();
console.log(names); // ["divesh", "mahesh", "jayesh"];
```

The time, the return of the method is not the final length of the array, as it is with array , as it is with array.push( ), rather, it's the value of the removed element. you have it in case you need it somewhere.

```javascript
const removedName = names.pop();
console.log(removedName); // 'sudesh'
```

This can be great for transferring data between two arrays or just giving a value one final use before poping in to void.

---

### **array.shift( )**

Shift works almost excatly like pop, with one major diffrence. it delets the first value in an major diffrence. it deletes the first value in an array and moves the rest backwards!
Exampel:

---

it too returns popped value.
ex:

---

### **array.unshift(value)**

if shift is the sister function to pop, unshift is that to push. it adds a new value to the start of an array insted of the end!

Example:

Much like push, it returns the new array length.

---

### **array.splice( )**

Now this one is a little more sophisticated, but don't worry we'll walk through it.

The splice method allows you to "splice" value into the array. it's first paramatere determines where the new element or elements are placed, the second how many after that point shoud be deleted placement and each subsequent condition is merely an element you wish to add.

Here is an example.

```javascript
const names = ["Divesh", ""];
```

it can also return an array of delete items, like pop!

```javascript
const removeValue = names.splice(0, 1);
console.log(removedValue); // xyx
```

### **array.slice( )**

And finally the slice function. This handy litle piece of code can make a new variable that contains every element from a certain point on in whatever array you feed it!

```javascript

```

Don't Worry, jon is still in the first array.

```javascript

```

---

**array.[index]**

- returns a certain value from an array.

**push(value)**

- adds the value to the end of the array

**pop()**

- removes the value from the start of the array

**shift( )**

- removes the value from the start of the array

**unshift(value)**

- adds the value to the start of the array

**splice(fromIndex, no_of_elements)**

- removes the number_of_elements, starting from index from the array

**slice(fromIndex , toIndex)**

- copies a certain part of the array

**concat( )**

- joint several arrays into one

**join('')**

- returns a string of array values

**array.length**

- returns the number of elements in the array

**reverse( )**

- reverse the order of the elements in the array

**toString()**

- returns a string representing the specified array and its element.

**includes(searchSlement)**

- determines wether an array includes a certain value among its entries, returning true of false as appropriate.

**sort( )**

- It sorts the elements of an array in place and returns the stored array. It sorts an array alphabetically.

**indexOf(searchElement)**

- returns the index of the first occurance of thet value

**lastIndexOf(searchElement)**

- returns the index of the last occurance of that value

**array.slice( )**

- And finally, the slice function. This handy little piece of code can make a new variable that contains every element from a certain point in whatever array you feed it!

### Array method for looping

array.forEach( )

- it executes a provider function once for each array element.

array.forEach((element,index) => {
// code block to be executed
})

**array.map()**

- it creates a new array populated with the result of calling a provided function on every element in the calling array.

```javascript
array.map((element, index) => {
  // code block to be executed
});
```

**array.filter()**

- it creates a new array with all elements that pass the test implementation by the provided function.

```javascript
array.filter(() => {
  //code block to be executed
});
```

**array.findIndex( )**

- it returns the index of the first element in the array that satisfies the provided testing function.

array.findIndex((el, idx, arr ) => {
// code block to be executed
})

**array.some( )**

- it tests wether at least one element in the array posses the test implemented by the provided function.

```javascript
array.some((el, index, array) => {
  // code block to be executed
});
```

**array.every( )**

- it tests wether all elements in the array pass the test implemented by the provided function. it returns a Boolean value.

```javascript
array.every((element, index) => {
  // code to be executed
});
```

**array.reduce( )**

- it runs a function on each array element to produce (reduce it to ) a single value. it works from left-to-right.

```javascript
aray.reduce((prevValue, currentValue, index, array)) => {
// code block to be executed
}
```
