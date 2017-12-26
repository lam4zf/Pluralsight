# H2 What is JavaScript?
- JavaScript has nothign to do with Java.  It pulled inspiration from the stucture, but it was named Javascript as a marketing ploy to take advantage of the popularity of Java.
- Created in 1995 by Netscape to create products and applications that run in the browser.
- It is primarily *client side*.  It only needs a browser to run.
- While it was originally designed as a scripting language, it is actually a fully featured language.

# H3 What can we do with JavaScript?
- Can be a ssimple as small enhancemnts like infinite scrolling.
- Parallax (parallax.js)
- Games in the browser
- For the "IoT": robots, wearable tech, and more
- Full applications (the Youtube app for Playstation built on AngularJS).

# H2 Lesson:1 Hello World: Writing Your First JavaScript
- Spacing doesn't matter
- `alert()` - just a popup
- `confrim()` - popup with the option to cancel
- `prompt()` - popup that can take input
```javascript
alert("Hello world!");
confirm("We will begin writing JavaScript now.");
prompt("Do you want to learn JavaScript?");
```

# H2 Lesson:2 Intro to Operators
- Basically, JavaScript can do math.  nothing new here
```javascript
console.log(2+2);
console.log(2-2);
console.log(1234*1234);
console.log(234512/123);
console.log(8%3);
```

# H2 Lesson:3 Understanding the Console
- gives feedback like messages, errors, and warnings, and allows you to test additional code with JavaScript that is currently running on the page.
- Add statements to print to the console from a js file or do it straight in the console itself.
```javascript
console.log("Hello world!");
console.warn("warning!!!");
console.error("ERROR!!!");
```

# H2 Lesson:4 String, Number, and Boolean Values
- Primitive Data Types
	- String
	- Number
	- Boolean
	- Null&ast;: a value that doesn't exist
	- Undefined&ast;: javascript doesn't understand how to interpret something

&ast; *these data types are weird.*
- Any *expression* in JavaScript will return a *value*(e.g. 2+2 returns 4), and that value will have a *type*.  For example, the result of 2+2 is 4 and 4's data type is a number.  If you add 2 + "2", the result is concatenated into the string "22".
- A value's *type* tells us what kind of "thing" it is.
```javascript
typeof(10 < 2); //returns boolean
typeof(300 /2); //returns number
typeof("Heelo"+"world"); //returns string
typeof(a + b); //returns undefined
typeof(3+"6"); //returns string
```

# H2 Lesson:5 Variables
- *Variables* allow us to store a reference to a value to be referred to alter or "remembered".
- When we create a new variable, we are *declaring* i.
- Variables are created using the `var` keyword.
- Varuable names cannot start with a number, contain spaces or use a reserved word.
- It also cannot use any punctuation except "_" or "$".
```javascript
var a = 2;
var b = 4;
typeof(a); //returns number
console.log(a+b); //6
typeof(a+b); //returns number

var myName = "Louis";
console.log(myName); // "Louis"
alert(myName); //" Louis"
```