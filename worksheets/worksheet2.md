# Introduction to JS

> Layik Hama

## Objects (more)
Almost "everything" is an object:

<ul>
  <li>Booleans can be objects (if defined with the <code class="w3-codespan">new</code> keyword)</li>
  <li>Numbers can be objects (if defined with the <code class="w3-codespan">new</code> keyword)</li>
  <li>Strings can be objects (if defined with the <code class="w3-codespan">new</code> keyword)</li>
  <li>Dates are always objects</li>
  <li>Maths are always objects</li>
    <li>Regular expressions are always objects</li>
  <li>Arrays are always objects</li>
  <li>Functions are always objects</li>
    <li>Objects are always objects</li>
</ul>

> Objects are mutable: They are addressed by reference, not by value.

In your console:
```js
x = 1
y = x //both x and y are 1
y = 3 //x is still 1
// or
x = 1
y = x
x = 3 //y is still 1

//however 
x = {value1: 1}
y = x
y.value1 = 3 //both just changed!
x.value1
```

### Accessing Object Properties
```js
var person = {
  firstName: "John",
  lastName : "Smith",
  age      : 55,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```

Now:

```js
person.property         // person.age
person["property"]      // person["age"]
//person[expression]    // x = "age"; person[x]
person[x = "age"]       // 55
```

You can delete age property using `delete` keyword/command:
```js
delete person.age;   // or delete person["age"]; 
```

### Methods
As you can see there is a `fullName` "function" (for objects we call them methods) and can be accessed as:

```js
// we need the brackets
person.fullName()
// 'John Smith'
```

## Loops
```js
for(x in person) console.log(x)
```
[![asciicast](https://asciinema.org/a/248702.svg)](https://asciinema.org/a/248702)

## Getters and Setters
I never use them. Are these coming from Java? There were shortcuts in Eclipse to create getters and setters, and synchronise in Xcode for ObjectiveC.

```js
var person = {
  firstName: "John",
  lastName : "Smith",
  language : "en",
  get lang() {
    return this.language;
  }
};

// use the getter
person.lang;
// see it person.language
// if it was a function called lang
// person.lang()
```

Similarly
```js
var person = {
  firstName: "John",
  lastName : "Smith",
  language : "",
  set lang(lang) {
    this.language = lang;
  }
};

person.lang = "en";
// again if function
// lang(lang) this.language = lang
// person.lang("en")
```

## Constructors

Remember functions (more on them later)?
```js
function add(x, y) {
  return(x + y)
}
```

We can also create objectsv(above) using functions. Above, we create just one person, now we can create "instances" of persons:

```js
function Person(first, last, age, eye) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eye;
}

// Create a Person object
var johnSmith = new Person("John", "Smith", 50, "blue");
```

Please note function names like other identifiers in JS are case sensitive.

Constructors are functions, except we want them to do someting else rather than just execute. We want them to reutn "the objet". If we follow the convetion and `not` return anuthing, our constructors would return `this` for us which is what we wnat.

If we do, well, that is what we get out of the `function`.

```js
function Person(first, last, age, eye) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eye;
}
// returns this with the four properties

// but
function Person(first, last, age, eye) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eye;
  return({
    name: first + " " + last,
    age: age,
    eye: eye
  })
}
// returns the object in return() statement
```

## Prototypes
> All JavaScript objects inherit properties and methods from a prototype.

* Date objects inherit from Date.prototype
* Array objects inherit from Array.prototype
* Person objects inherit from Person.prototype

> The Object.prototype is on the top of the prototype inheritance chain:

Therefore:

```js
Date.prototype
// Date {}

// but
Object.prototype
// {}
```

One would be forgiven to confuse prototypes and constructors. Constructors are just functions which create objects. Constructors are the building blocks of JavaScript.

At this stage, I would stay away from modifying prototypes.


## Functions (more)
JavaScript is a "functional" language. Functions rae building blocks just like primitives (string, number)
```js
var x = function (a, b) {return a * b};
var z = x(4, 3);
```

> Functions can also be defined with a built-in JavaScript function constructor called Function().

..but we will avoid this.

As JS hoists your code, you don't have to worry about the order of using your functions.

```js
// this is fine
myFunction(5);

function myFunction(y) {
  return y * y;
}
```

### Self invocation
Because functions are used almost everywhere in JS, they can also invoke themselves:

```js
(function () {
  alert("Hello World");  
})(); // the enclosing brackets followed by the last () means run the function within.
```
> Functions are Objects

But `typeof` will return `function`, so you can always check if what you are about to `call` is a function:

```js
if(typeof(person.fullName) === 'function') { 
  // just made 100% sure that what we are about to call is a function so we can call it.
  person.fullName()
}
```

Very helpful method of all functions is `toString`, which for Java developers should be familiar, returns the actual body of the function:

```js
person.fullName.toString();
// function() { return this.firstName + " " + this.lastName; }
```

### Parameters

First of all:
```js
function args(a, b) {
  return arguments.length;
}
args()
// 0
args(1,2,3)
// 3
```
Will be handy once you start checking parameters. But just good to refer back to for now.

> Arguments are Passed by Value
Let us learn this.

> Objects are Passed by Reference
Pay good attention to this.