# The "new" Keyword

new keyword have multiple aspects related to it but for now let's just consider the most basic functionality the new key word performs.
It creates a new object.

yes that's it. Not so difficult to grasp right? new keyword creates a new empty object. Enough of talking lets dive in to code and create same person object from our last lecture but this time using the new keyword.

```javascript
const person = new Object();
```

What this single line of code did is created an empty object calles "person". by empty i mean there are no properties attached to it, its literally empty like person = {}.
We can treate this oobject same like the person object from our previous example. We can add new properties to this object like we did before.

```javascript
newPerson.lastName = "Thakre";
```

and we can access this properties exacatly like before.

```javascript
console.log(person.lastname); // 'Thakre'
```

lets see the typeof person object created with new keyword.

```javascript
console.log(typeof person); // object
```

So the most basic thing that new keyword performs is created an empty object.
You might be wondering that what is the line **_const person = new Object();_** what the Object( ) keyword is? and why its used in combination to the **_new_** keyword ?

Well don't worry lets explore this  
Object Methods, Object( ) also known as Object Constructor or Object Method is default Constructor method provided by javascript to create objects.
Javascript provide us ability to create our own object constructor and create new objects from its type. Don't belive me ? lets give a try.

```javascript
function person(name, age, profession) {
  this.name = name;
  this.age = age;
  this.profession = profession;
}
const john = new person("Divesh", 19, "Teacher");
console.log(person.name);
```

what we did instead of using a default constructor provided by js to us we created our own constructor method "Person" and than created an object of person type and than created an object of person type out of it.

we can also create our object like.

```javascript
const Divesh = new person();
```

creating an object with empty constructor woud initilise its properties with undefined and not null.
i know the this keyword is bothering you but don't worry its comming next.

---

## 'new' and 'this' keyword

this keyword is treated diffrently depending on the execution context but foe now lets only discuss the relation between this and new keywords.
"new keyword binds this to object itself"

### The this keyword

so first of all what is the "This keyword" and what is used for, well the this keyword is used to refrence the object that is executing the current function that coonsole.log's a string using this keyword it would a little like this.

```javascript
function Sentence(words) {
  this.words = words;
  console.log(this);
}

const S = new Sentence("learning about This keyword");
```

so let's see what is going on here.
first off we set a function with input "Words", and inside this we set "this.words", and inside this we console.log this and create a variable that constsins a new input for our sentence, but since this keyword equals to our input, it'll console.log our new input.
