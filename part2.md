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

```javascript
const str = "Hello Universe";
const capetalStr = str.toUpperCase();
console.log(str); // 14 (it also count spaces)
```
