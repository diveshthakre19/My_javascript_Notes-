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
