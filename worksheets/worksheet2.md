# Introduction to JS

> Layik Hama

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
  lastName : "Doe",
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
  lastName : "Doe",
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