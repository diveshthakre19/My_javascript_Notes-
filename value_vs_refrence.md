JavaScrit difrentiates Data Types on:

- **Primitive values**
  (Number, string, Boolean, Null, Undefined...)

- **Complex values**
  (Object, Arrays)

## Copying Primitive Values:

When copying primitive values, javascript is going to behave as we expect it to. you just need to see what was the value of the variable at the time of the assignment.

Let me give you a few real examples:

## Copying Numbers

```javascript
let x = 1;
let y = x;

x = 2;
console.log(x); // 2
console.log(y); // 1
```

## Copying Strings

```javascript
let firstPerson = "Divesh";
let secondPerson = firstPerson;

firstPerson = "Shantanu";

console.log(firstPerson); // 'Shantanu'
console.log(secondPerson); // 'Divesh'
```

## Copying Complex Values:

When copying complex values, javascript engiene is not gooing to be as you woud initially think it would.
Let me give you an example.

### copying Arrays

```javascript
const animals = ["dogs", "cats"];
const otherAnimals = animals;
animals.push("llamas");
console.log(animals); // ['dogs', 'cats' llamas']
console.log(otherAnimals); // ['dogs', 'cats' llamas']
```

Wait What?! What happend here? Why are both arrays the same if we only pushed the values to the first array?

Something just dosen't feel right, right?
Let's try something similar with objects to see wether the behaviour continues.

### Copying Objects

```javascript
const person = {
  firstName: "Divesh",
  lastName: "Thakre",
};
const otherPerson = person;
person.firstName("Shantanu");

console.log(person); // {firstName:'Shantanu', lastName:'Thakre'}
console.log(otherPerson); // {firstName:'Shantanu', lastName:'Thakre'}
```

What?! Again, this dosen't look right. so... What happened here? Well...

When a variable is assigned a primitive value, it just copies that value. We saw that number and examples.

On the other hand, when a variable is assigned a non-primitive value (such as an object, an array or a function), it is given a refrence to that object's location in memory.
What dose that mean ?

In this example above, the variable otherPerson dosen't actually contains the value
{firstName:'Divesh', lastName:'Thakre'}, instead it points to a location in memory where that value is stored.

What?! Again, this dosen't look right. so... What happened here? Well...

```javascript
const otherPerson = person;
```

When a refrence type value is copied to another variable, like otherPerson in the example above, the object is copied by refrence instead of value. In simple terms, person and otherPerson don't have their own copy of the value. They point to the same location in memory.

```javascript
console.log(person); // {firstName:'Shantanu', lastName:'Thakre'}
console.log(otherPerson); // {firstName:'Shantanu', lastName:'Thakre'}
```

When a new item is pushed to **person**, the array in memory is modified, and as a result the variable is modified, and as a result the variable otherPerson also reflects that change.

We're never actually making a copy of a person object. were just make a variable that points to the same location in the memory.

### Equality

We can prove that with a simple equality check.

```javascript
const person = { firstName: "Divesh" };
const otherPerson = { firstName: "Divesh" };
console.log(person === otherPerson);
```

What do you think? Are person and otherPerson equal? Well, they shoud be, right?

Thwy look excatly the same, have the same key and values. Let's check it out:

```javascript
console.log(person === otherPerson); // false
```

You might expect person === otherPerson to resolve to true but that isn't the case. The reason behind that is althought the person and the otherPerson contains identical objects, they still point to distinct objects stored in diffrent locations in memory.

Now, let's create a copy of the person object by copying the object itself, rather than creating a completly new instance of it.

```javascript
const anotherPerson = person;
console.log(person === anotherPerson); // true
```

person and anotherPerson holds refrence to the same location in the memory and are therefore considered to be equal.
Awesome! We just learned that primitive values are copied by values, and that object are copied by refrence.
Up next we're going to learn how to make a real copy of an object. That will allow us to copy an object and change it without being afraid that we'll change both objects at the same time.

---

## Shallow Cloning

We've seen all the problems we could possibly encounter if we tried changing values of an object copied by a refrence. so how can we properly copy it and remove a refrence. So how can we properly copy it and remove a refrence? how can we create a complete clone of the object?

### Cloning Arrays:

**1st way: Spread Operator**
Speread operator is a newer addition to javascript.Before using it to clone an object Without keeping a refrence.

let's first explore how it works.
Imagine you had an array:

```javascript
const numbers = [1, 2, 3, 4, 5];
const newNumbers = [...numbers];
```

How coud we use the spread operator on this array? Spread synatx allow us to "Spread" the values of strings, objects and arrays.

How dose it Work? Let's see it in action on our numbers array.

The synatx of a spread operator is represented just by three dots.

```javascript
console.log(...numbers); // 1, 2, 3, 4, 5
```

We get back all the values from the array individually, one after the other, they got taken out of the array. So how can we make use of this?

Take a look at the following code. in there, we create a new variable, and in it we put a completly new, empty array, in which we spread the values of our original array.

```javascript
const newNumbers = [...numbers];
console.log(newNumbers); // [1, 2, 3, 4, 5]
```

We get an array that looks identical to the one the one that we had at the begining, but is it completly identical? let's check the equality, we're going to create another copy and then compare them.

```javascript
const copiedNumbers = numbers;
console.log(numbers === copiedNumbers); // true
console.log(numbers === newNumbers); // false
```

We got back true and false. What dose this mean? This means that the copiedNumbers array is pointing to the same place in the memory where the original numbers array is pointing to.
Therefore, if we change one, or the other, they woud both change. And we do not want that.
On the other hand, numbers and newNumbers are not the same. They represent a completly diffrent array. Let's try changing the original numbers array:

```javascript
numbers.push(6);

console.log(numbers); // [1, 2, 3, 4, 5, 6 ]
console.log(copiedNumabers); // [1, 2, 3, 4, 5, 6 ]
console.log(newNumbers); // [1, 2, 3, 4, 5 ]
```

As you can see, the **numbers** and **copiedNumbers** both got changed. And the aray with we created using the spread operator was unchanged! This means that we created something called a "Shallow clone". The "shallow" part is going to make sense once we introduce the "**deep clones**"

---

**2st way: Array.slice()**

```javascript
numbers = [1, 2, 3, 4, 5];
numbersCopy = numbers.slice();
// [1, 2, 3, 4, 5]
```

### Cloning Objects

**1st way: Spread Operator**
We can clone the object using the speread operator as well.

```javascript
const person = {
  name: 'div'
  age: '20'
}

const otherPerson = {...person}
```

...now we can change the **otherPerson** without changing person:

```javascript
otherPerson.age = 21;
console.log(person); // unchanged
console.log(otherPerson); // changed
```

**2nd way: Object.assing()**

```javascript
var A1 = { a: "2" };
var A2 = Object.assing({}, A1);
```

Awesome! we just learned two diffrent ways for cloning boyh objects and arrays! As I mentioned, the ways of cloning we just explore create SHALLOW CLONES.

### Deep Cloning

```javascript
const person = {
  firstName: "Random",
  car: {
    brand: "toyota",
    color: "black",
    wheels: "4",
  },
};
```

Now.. let's try to creating a copy of that object, in one of the ways we've learned now:
For example, we can use the spread operator:

```javascript
const newPerson: = {...person};
```

Great, we've learnesd that this removes the refrence from the original object, right?

so let's try changing the newly created object:

```javascript
newPerson.firstName = "Steve";
```

let's console logging both objects and see what changed? Without reading you can try to answer.

```javascript
console.log(person); // unchanged
console.log(newPerson); // changed
```

As we learn, if we use the spread operator, the refrence to the initial objects gets deleted therefore we can change the new object without having to worry!

Oh, if only it were that simple... let's see what woud happen if we tried changing the properties of steve's car.

```javascript
newPerson.car.color = "red";
```

...and then console.log both objects:

```javascript
console.log(person); // changed
consloe.log(newPerson); // changed
```

Both objects got changed. How did that happen?
Well... we only remove the refrence from the outer object, the person one , but notice how the car is also an object...

It has it's own refrence, and the same rules apply... if we want a real copy, we need to remove a refrence from the inner object as well.

we coud do that by spreading the properties of an inner object:

```javascript
const newPerson = { ...person, car: { ...person.car } };
```

If we now tried changing the properties of the car, it woud only change them on the newly created object, let's try it out:

```javascript
newPerson.car.color = "red";
console.log(person); // unchanged
console.log(newPerson); // changed
```

That's great! But this only works for two levels into depth, first level is when we're inside of the person object, and second level is when we're inside of the **car** onject.

But if we had more nested objects, we'd need to spread everything. And that's not the solution. When we have deeply nested objects, we need to create a deep clone. for an object to be a deep clone, it needs to destroy all the refrences.

There are two methods that are going to make this extremely easy for us. First one is called JSON.stringify and the second one is called JSON.parse. Let's see them in action, we can use the same person object we declared above:

```javascript
const person = {
  firstName: "Steve",
  car: {
    brand: "Toyota",
    color: "black",
    wheels: "4",
  },
};
```

...first, we're going to use JSON.stringify method. The JSON.stringify() method converts a javascript object or any value to a string. During this process, all the refrence are destroyed.

```javascript
const stringifiedPerson = JSON.stringify(person);
console.log(stringifiedPerson);
```

The thing that we get back is a string... That isn't all that valuable to us. How do we turn it back to an object again? We can do that by using JSON.parse method:

```javascript
const newPerson = JSON.parse(stringifiedPerson);
console.log(newPerson);
```

The JSON.parse() method parse a string, constructing the Javascript value or object contained in the string.

Before we start testing it out, there's one simple tweak we can do it in one line:

```javascript
const newperson = JSON.parse(JSON.stringify(person));
```

Awesome! We got our object back. let's prove that all of the refrences are indeed deleted and that all the refrences are indeed deleted and that all of the refrences are indeed deleted and that the newPerson is indeed a deep clone.

```javascript
newPerson.firstName = "Steve";
newPerson.car.color = "red";

console.log(person); //unchanged
console.log(newPerson); //changed
```

That's it! you have learned one on the toughest topics in the whole Javascript! If you're still a bit confused, that's completly normal.

---
