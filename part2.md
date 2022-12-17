## 10. Strings

> strings stores the sequence of characters.

- In javaScript strings can be used to store some kind of data in Textform.
- strings can be created by wraping characters in to "Double Quotes" as well as 'single Quotes'.

```javascript
const sampleString1 = "this is a string";
const sampleString2 = "this is also a string";
```

## Template Literals

> Template literals uses ``Backtics instead of the quotes.

- Backtics allow us to inject quotes inside the strings.
- With this synatx we can inject variables inside the strings.

```javascript
const sampleString1 = `They said "keep trying".`;
const usedId = 449:

const user1 = `my user id is ${usedId}`
console.log(user1) // `my user id is 449`
```

---

## String methods

- The most used operatror we use with strings is .length, with this we can print the length of string

```javascript
const string1 = "Hello Universe";
console.log(string1.length); // 14 (it also count spaces)
```

### toUpperCase()

> The toupperCase() method in JavaScript is used to convert all the characters in a string to uppercase. This method does not take any arguments and returns the new string in uppercase.

- toupperCase() method is a simple and effective way to convert a string to uppercase in JavaScript.

```javascript
const str = "Hello Universe";
const upperStr = str.toUpperCase();
console.log(upperStr); // 'HELLO UNIVERSE'
```

---

### toLowerCase()

> The toLowerCase() method in JavaScript is a string method that converts all the letters in a string to lowercase. This method does not affect any other characters in the string, such as numbers or special characters. It only converts the letters to lowercase.

```javascript
const str = "HELLO UNIVERSE";
const lowerStr = str.toUpperCase();
console.log(lowerStr); // 'hello universe'
```

---

### .trim() method

> In JavaScript, the trim() method is used to remove whitespace from the beginning and end of a string. This can be useful when you want to make sure that the data you're working with doesn't have any unnecessary whitespace at the beginning or end.

```javascript
const str = "       extra whiteSpace     ";
const trimedStr = str.trim();
console.log(trimedStr); //'extra whiteSpace'
```

---

### .concat()

> The concat method in javascript strings is used to combine multiple strings into one. It takes in one or more strings as arguments and returns a new string that contains the concatenated values of all the strings passed as arguments.

For example, the following code:

```javascript
let firstName = "Divesh";
let lastName = "Thakre";
let age = "19";
let details = firstName.concat(lastName, age);
console.log(details); // 'DiveshThakre19'
```

- To combine multiple strings we canuse + operator can be used .

```javascript
let firstName = "Divesh";
let lastName = "Thakre";
let details = firstName + lastname;
console.log(details); // 'DiveshThakre'
```

---

### Convert strings into Numbers

```javascript
let userInput = "19";
console.log(typeof userInput); // string
let userAge = Number(userInput);
console.log(typeof userAge); // number
```

### Convert Number into Strings

```javascript
let userInput = 8547547545677247542587;
console.log(typeof userInput); // number
let userPassword = String(userInput);
console.log(typeof userPassword); // string
```
