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

Remember functions?
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