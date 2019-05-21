# Introduction to JS

## The console
Open your favourite browser, find "Developer tools" and open the "console tab".

Say hello to your world:

```javascript
alert("Hello World!");
```

<img width="459" alt="Screenshot 2019-05-17 at 16 28 58" src="https://user-images.githubusercontent.com/408568/57938823-e4d92200-78c0-11e9-9a42-8a4c1b86f451.png">

Or right within this Markdowb document:
```javascript
<script>
document.write("Hello World");
</script>
```
<script>
document.write("Hello World");
</script>

The browser console can be your calculator if you don't usually do it in Google:

```javascript
1 + 1
```

<img width="499" alt="Screenshot 2019-05-17 at 16 25 47" src="https://user-images.githubusercontent.com/408568/57938639-7ac07d00-78c0-11e9-9bd8-10fd540b32ba.png">

Let us do some of the [w3](https://www.w3schools.com/js/js_intro.asp):

* First let us try the original code
* Then let us try a fontawesome version of it.

## \<script> tag
> Placing scripts at the bottom of the <body> element improves the display speed, because script interpretation slows down the display.

- See example in using [w3](https://www.w3schools.com/js/tryit.asp?filename=tryjs_whereto_body) 
- Local repo (*/html/myscript.html*) with corrections in the original JS.

```javascript
<script>
document.write(5 + 6);
</script>
```
<script>
document.write(5 + 6);
</script>

See the same command over at [w3](https://www.w3schools.com/js/tryit.asp?filename=tryjs_output_write).

## The 'document'
> The HTML DOM document object is the owner of all other objects in your web page. ~ W3

```javascript
document.getElementById(id)	          // Find an element by element id
document.getElementsByTagName(name)	  // Find elements by tag name
document.getElementsByClassName(name)     // Find elements by class name
```
Creaete a list item and add it to an unordered list: [W3](https://www.w3schools.com/jsref/tryit.asp?filename=tryjsref_node_appendchild).

```javascript
var node = document.createElement("LI");
var textnode = document.createTextNode("Water");
node.appendChild(textnode);
document.getElementById("myList").appendChild(node);
```

Let us play in the console, open the [W3](https://www.w3schools.com/js/js_htmldom_document.asp) page:

```javascript
document.getElementsByTagName("table") // returns 10 tables?
document.getElementsByClassName("w3-table-all") // 5?
var row = document.createElement("tr");
var td = document.createElement("tr");
var textnode = document.createTextNode("Hello World");
td.appendChild(textnode)
row.appendChild(td)
document.getElementsByClassName("w3-table-all")[0].appendChild(row)
```
### Output

* `innerHTML` (element)
* `document.write()` (print?)
* `window.alert()` (special)
* `console.log()` (print?)

```js
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = 5 + 6;
</script>
```

## Syntax
Variable declaration

```js
var a, b, c;// Declare 3 variables
a = 5;      // Assign the value 5 to a
b = 6;      // Assign the value 6 to b
c = a + b;  // Assign the sum of a and b to c
```
### Data types (or types)
Please do some `typeof` checks on variables and see if they match these. For example:

```js
typeof(null)
typeof(1)
typeof("Hello World")
```
<table>
 <thead>
  <tr>
   <th scope="col">Type</th>
   <th scope="col">Result</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Undefined</td>
   <td><code>"undefined"</code></td>
  </tr>
  <tr>
   <td>Null</td>
   <td><code>"object"</code></td>
  </tr>
  <tr>
   <td>Boolean</td>
   <td><code>"boolean"</code></td>
  </tr>
  <tr>
   <td>Number</td>
   <td><code>"number"</code></td>
  </tr>
  <tr>
   <td>String</td>
   <td><code>"string"</code></td>
  </tr>
  <tr>
   <td>JS Function</td>
   <td><code>"function"</code></td>
  </tr>
    <tr>
   <td>Any other object</td>
   <td><code>"object"</code></td>
  </tr>
 </tbody>
</table>

Table from Mozilla [documentations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof).

### Strings
Use any of three types of "quotes":

```js
// "Hello", 'Hello', `Hello`
("Hello" === 'Hello') === (`Hello` === "Hello") // true
```

### Operators

<table>
<tbody><tr>
<th style="width:25%">Operator</th>
<th>Description</th>
</tr>
<tr>
<td>+</td>
<td>Addition (concatenation)</td>
</tr>
<tr>
<td>-</td>
<td>Subtraction</td>
</tr>
<tr>
<td>*</td>
<td>Multiplication</td>
</tr>
<tr>
<td>**</td>
<td>Exponentiation (ES2016)</td>
</tr>
<tr>
<td>/</td>
<td>Division</td>
</tr>
<tr>
<td>%</td>
<td>Modulus (Division Remainder)</td>
</tr>
<tr>
<td>++</td>
<td>Increment</td>
</tr>
<tr>
<td>--</td>
<td>Decrement</td>
</tr>
</tbody></table>

Table from [W3](https://www.w3schools.com/js/js_operators.asp).

Careful with `+` operator:
```js
var x = 5 + 5;      //10
var y = "5" + 5;    //55
var z = "Hello" + 5;//Hello5
```

<table>
<tbody><tr>
<th style="width:12%">Operator</th>
<th>Description</th>
</tr>
<tr>
<td>==</td>
<td>equal to</td>
</tr>
<tr>
<td>===</td>
<td>equal value and equal type</td>
</tr>
<tr>
<td>!=</td>
<td>not equal</td>
</tr>
<tr>
<td>!==</td>
<td>not equal value or not equal type</td>
</tr>
<tr>
<td>&gt;</td>
<td>greater than</td>
</tr>
<tr>
<td>&lt;</td>
<td>less than</td>
</tr>
<tr>
<td>&gt;=</td>
<td>greater than or equal to</td>
</tr>
<tr>
<td>&lt;=</td>
<td>less than or equal to</td>
</tr>
<tr>
<td>?</td>
<td>ternary operator</td>
</tr>
</tbody></table>
Table from [W3](https://www.w3schools.com/js/js_operators.asp).

### functions

```js
function toCelsius(fahrenheit) {
  return (5/9) * (fahrenheit-32);
}
document.getElementById("demo").innerHTML = toCelsius; 
```

Example:
```js
var x = toCelsius(77);
var text = "The temperature is " + x + " Celsius";
```

> A variable that has not been assigned a value is of type undefined. A method or statement also returns undefined if the variable that is being evaluated does not have an assigned value. A function returns undefined if a value was not returned. 
~ [Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

```js
// undefined
var a;    //returns undefined
var s = a;//returns undefined
s = 3;    //returns 3

// so does
function silent(x) {
    var a = x;
}
// undefined
```
## Objects
<table style="color:black;margin:6px 0; background-color:white">
<tbody><tr>
<th style="width:370px">
Object
</th>
<th>
Properties
</th>
<th>
Methods
</th>
</tr>
<tr>
<td>
<img src="https://upload.wikimedia.org/wikipedia/commons/3/3b/BicyclePlymouth.jpg" style="height:230px;">
</td>
<td>
<br>bike.name = Old<br><br>
bike.model = Plymouth<br><br>
bike.weight = 10kg<br><br>
bike.color = black
</td>
<td>
<br>bike.ride()<br><br>
bike.fix()<br><br>
bike.brake()
<br><br>bike.enjoy()</td>
</tr>
</tbody></table>

An object could be 

```js
var person = {
  firstName: "John",
  lastName : "Smith",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```

### this
From [w3](https://www.w3schools.com/js/js_this.asp) docs:
<ul>
<li>In a method, <code >this</code> refers to the <b>owner object</b>.</li>
<li>Alone, <code >this</code> refers to the <b>global object</b>.</li>
<li>In a function, <code >this</code> refers to the <b>global object</b>.</li>
<li>In a function, in strict mode, <code >this</code> is <code >undefined</code>.</li>
<li>In an event, <code >this</code> refers to the <b>element</b> that received the event.</li>
<li>Methods like <code >call()</code>, and <code >apply()</code> can refer <code >this</code> to <b>any object</b>.</li>
</ul>

On its own, look at [this](https://www.w3schools.com/js/tryit.asp?filename=tryjs_this). Or type this in your console:

```js
var x = this;
document.write(x);
```

## Scope
```js
// code here can NOT use carName

function myFunction() {
  var carName = "Volvo";
  // code here CAN use carName
}

// code here can NOT use carName 
```

`var` has no scope, `let` has scope:

```js
 var x = 10;
// Here x is 10
{
  let x = 2;
  // Here x is 2
}
// Here x is 10 
```
Try this in your browser console:
```js
// in your console
{var x = 10}
// type x
{let x = 2; console.log(x)}
// 10
// undefined
// type x

```

## Hoisting
```js
console.log(x) // 5
x = 5;         // Assign 5 to x
var x;         // Declare x
```

# ECMAScript
> ECMAScript 3 is fully supported in all browsers.

> ECMAScript 5 is fully supported in all modern browsers.