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
document.getElementById(id)	          # Find an element by element id
document.getElementsByTagName(name)	  # Find elements by tag name
document.getElementsByClassName(name)     # Find elements by class name
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