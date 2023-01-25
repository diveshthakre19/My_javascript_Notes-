# Strings Intro

In javascript, and in any programing language for that mater, we need to store text.
in javascript we use strings to store text. String is nothing more than a primitive data type .
How we can create strings in javascript?

There are a few ways:

```javascript
const double = " This is a string written inside of double quotes";
const single = " This is string written inside of  single quote";
const backticks = `This is string written inside of  backticks `;
```

Strings created with single and double quotes are the same. We can call them simple or basic strings. They simply represent some static textual value.

Strings created with backticks on the other hand provide extended functionality. They are dynamic. They allow us to execute real javascript logic inside them. Let me show you What i mean in an example:

```javascript
const variableName = `${2 + 2 } // 4
```

Everything that we put in between the dollar sing and curly brackets is not simply taken for granted. It is eveluated as javascript logic.
Therefore, 2 + 2 returns 4, rather than the string of "2 + 2".

That means that we can also make function calls inside of backticks strings, for example:

```javascript
const sum = (a, b) => a + b;

const total = `The sum is ${sum(2, 2)}`; // The sum is 4
```

Backtick strings have one extra feature. We can span them across multiple lines.

```javascript
const numbers = `
    1
    2
    2
`;
```

if we tried doing this with basic single or double quotes strings, We would get an error.

Let me ask you one question, how would the value of the following string look like?

```javascript
const greeting = 'hi, I'm Divesh';
```

This would produce an error. in here, with a single quote after the I , we actually end the string. And javascript donen't Know how to eveluate the rest of the code.
One way to fix this woud simply be to use diffrent type of quotes. For example:

```javascript
const greeting = "Hi, I'm Divesh ";
```

But this is not a solution. Imaginge if we had both types of the strings in the sentence.

```javascript
const greeting = "Hi, I'm Divesh, "Thakre."
```

This would, again, break.
There's something called "escape character", Which allows us to treate special character like normal letters. This is how we can escape the single and double quotes.

```javascript
const greeting = ' Hi, I\'m Divesh, "Thakre".';
```

But this is getting messy. We still have "cool"
strings at our diaposal right ? Let's use them.

```javascript
const greeting = `Hi, I'm Divesh, "Thakre".`;
```

This way, we can write the string however we want. Great!

## String Escape Characters

\ ' Single quote

\ " Double quote

\ \ Backslash

\b Backspace

\f Form feed

\n New line

\r Carriage return

\t Horizontal Tabular

\v Vertical Tabular

---

## String length and basic properties

One thing that we often want to know when it comes to strings is its length.
You might think that we nees to do some complex stuff to come to that value. Like loop throught all the characters, count them and then display the value. it's so much simpler than that.

```javascript
const name = "Divesh";
name.length; // 6
```

Another thing we might want to do is get the element at a cretain position often is get the element at a certain position of the string. We can do it really easily as well.

This is how we woud get the first letter of a string:

```javascript
name.[0] // D
```

...and this is how we woud get the last letter:

```javascript
name.[name.length - 1] // h
```

Let's inspect this line for a movement.
name.length is equals to 6 and 6 minus 1 is 5 name of 5 is the last letter, because we start from 0 and not from 1. For a reason that string starts from 0, we need to do it like this.
In the same fasion, we can get any character in the string.

```javascript
name.[2] // v
```

Great! In this part, we learn how to get a length of the string using the length property, as well as how to get certain characters of a string!

Now let's learn how we can change the case of the string!

---

## Change string case

In this article we're going to learn how we can change the case of a string. What is the case? you have definately hered about upperCASE amd lowerCASE letters. That's it!

In javascript, we have only two really simple and staringt forward methods for changing the character case and they are:

## string.toLowerCase( )

## string.toUpperCase( )

Let's understand with this example:

```javascript
const string = " Hello! How are you, Divesh?";

string.toLowerCase(); // "hello! how are you, divesh?"
string.toupperCase(); // "HELLO! HOW ARE YOU, DIVESH?"
```

Notice how we have parantheses on these two. That's because they are functions, more precisely:methods we call on a string.
Let's learn more useful string methods!

---

## Searching for a Substring

There are multiple ways to look for a substring with a string.

## str.indexOf( )

The first method is str.indexOf(substr, pos)
It looks for the substr in str, starting from the given position pos, and returns the positions where the match was found or -1 if nothing can be found.

Fro instance:

```javascript
const string = "I love cars, he said, cars are great!";
string.indexOf("cars"); // 7
string.indexOf("Cars"); // -1
```

The optional second parameter allow us to search starting from the given position.
For instance, the first occurrence of 'cars' is at psition 7. To look for the next occurrence, let's start the search from position 8:

```javascript
string.indexOf("cars", 8); // 22
```

---

## str.lastIndexOf( )

str.lastIndexOf(substr, position)
There is also a similar method
str.lastIndexOf(substr, position) that searches from the end of a string to its beginning

Great! Now you can use indexOf methods if you need to find the exact position of some substrings in a string.

---

## includes( )

But meuch more often you're just intersted if a string constins something, and you're not concrened where is it in the string.
For these case you can use string.includes( )
It simply returns true or false.
It's right choice if we need to test for the match, but don't need its position:

```javascript
const string = "I love cars, he said, cars are great!";
string.includes("cars"); // true
```

As with the indexOf method, he optional second argument of str.includes is the position to start searching from.

---

## str.startsWith( ) and str.endsWith( )

The method str.startswith and str.endsWith do exacatly what they say:

```javascript
string.startsWith("I"); // true
string.endsWith("cars"); // false
```

The best method for getting a substring of a string is str.slice( ).

Let's show it on an example:

---

## str.slice(start [, end])

Returns the part of the string from start to (but not including) ens. For instance:

```javascript
const exampleString = "javascript'
exampleString.slice(4,10) // script
```

some times, we might want to split the string into multiple substrings. For that we'll be using a string method calles split( ).

Let me give yoou some examples:
This is how we can split a word into characters:

```javascript
const exampleString = "dog";
console.log(exampleString.split("")); //(3) ['d', 'o', 'g']
```

Notice how we passed an empty string as a first parametere of a split method.
This is how we can split a sentence in words:

```javascript
const string = "The quick brown fox jumps over the lazy dog.";
console.log(string.split(" ")); //(9) ['The', 'quick', 'brown', 'fox', 'jumps', 'over', 'the', 'lazy', 'dog.']
```

The result of both examples is an array!
Exacatly.

---

## Reverse a string

## REVERSE

There isn't a built in string method that reverses a string. Rather, we can use the knowledge we previously gained! Remember how we can split a string into array characters? Array do have a reverse method.
So this is a process.

1. Split a string
2. Reverse newly created a array
3. Turn the array into string using join( )

```javascript
const str = "test";
str.split("").reverse().join(""); // tset
```

---

## REPEAT

let's say you want to repeat a string an x number of times. you can do that using the string.repeat( ) method.

```javascript
const dogSays = "woof";
console.log(dogSays.repeat(4)); // woofwoofwoofwoof
```

---

## TRIM

Sometimes, users don't know how to type. And we need to clean empty spaces using trim.

```javascript
const str = "     Hello World!     ";
console.log(str.trim()); // "Hello World"
```
