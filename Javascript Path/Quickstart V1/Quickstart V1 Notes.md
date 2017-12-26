https://app.pluralsight.com/library/courses/quick-start-javascript-1-1870

## What is JavaScript?
- JavaScript has nothign to do with Java.  It pulled inspiration from the stucture, but it was named Javascript as a marketing ploy to take advantage of the popularity of Java.
- Created in 1995 by Netscape to create products and applications that run in the browser.
- It is primarily *client side*.  It only needs a browser to run.
- While it was originally designed as a scripting language, it is actually a fully featured language.

### What can we do with JavaScript?
- Can be a ssimple as small enhancemnts like infinite scrolling.
- Parallax (parallax.js)
- Games in the browser
- For the "IoT": robots, wearable tech, and more
- Full applications (the Youtube app for Playstation built on AngularJS).

## Lesson 1: Hello World: Writing Your First JavaScript
- Spacing doesn't matter
- `alert()` - just a popup
- `confrim()` - popup with the option to cancel
- `prompt()` - popup that can take input
```javascript
alert("Hello world!");
confirm("We will begin writing JavaScript now.");
prompt("Do you want to learn JavaScript?");
```

## Lesson 2: Intro to Operators
- Basically, JavaScript can do math.  nothing new here
```javascript
console.log(2+2);
console.log(2-2);
console.log(1234*1234);
console.log(234512/123);
console.log(8%3);
```

## Lesson 3: Understanding the Console
- gives feedback like messages, errors, and warnings, and allows you to test additional code with JavaScript that is currently running on the page.
- Add statements to print to the console from a js file or do it straight in the console itself.
```javascript
console.log("Hello world!");
console.warn("warning!!!");
console.error("ERROR!!!");
```

## Lesson 4: String, Number, and Boolean Values
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

## Lesson 5: Variables
- *Variables* allow us to store a reference to a value to be referred to alter or "remembered".
- When we create a new variable, we are *declaring* i.
- Variables are created using the `var` keyword.
- Varuable names cannot start with a number, contain spaces or use a reserved word.
- It also cannot use any punctuation except "&lowbar;" or "$".

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

## Lesson 6: Using Variables
```javascript
var myFavoriteMovie = prompt("What is your favorite movie?");
alert("My favorite movie is " + myFavoriteMovie);

var randomNumber = Math.random(); //generate a random decimal between 0 and 1; multiply by 5 for 1 - 5
```

## Lesson 7: Intro to Control Flow: if/else statements
- Use conditional logic and `if/else` statements to determine which code is executed.
```javascript
var answer = prompt("What is the capital of New York?");

if(answer === "Albany"){ //she didn't explain 3 vs 2 here
	alert("You are correct");
}
else {
	alert("u wrong. " + answer + " is not right.");
}
```

## Lesson 8: Using if/else
- JavaScript can support `else if` statements as well.
```javascript
var answer = prompt("What is the capital of New York?");

if (answer === "Albany"){ //she didn't explain 3 vs 2 here
	alert("You are correct");
}
else {
	alert("u wrong. " + answer + " is not right.");
}

var favoriteAnimal = prompt("What is your favorite animal?");

if (favoriteAnimal === "Panda"){
	alert("panda panda panda panda");
}
else if (favoriteAnimal === "dog"){
	alert("I have a dog");
}
else {
	alert(favoriteAnimal + "s are pretty cool");
}
```

### FizzBuzz
- *Generate a random number between 0 and 5.  If result is divisble by 3, alert "fizz",  if the nubmer is divisible by 5, alert "buzz", otherwise print number to console.*
```javascript
var rand = Math.round( Math.random() * 5);

if(rand % 3 === 0){
	alert("fizz");
}
else if(rand % 5 === 0){
	alert("buzz");
}
else{
	console.log(rand);
}
```

## Lesson 9: Control Flow and Comparison Operators
- We are going to modify the previous FizzBuzz assignment to be more like the real problem.
- *Generate a raondom whole number between 0 and 15.  If result is divisble by 3, alert "fizz",  if the nubmer is divisible by 5, alert "buzz", otherwise print number to console.  If a number is divisible by 3 AND 5, alert fizzbuzz.  If the random number is 0, it should not return any text.*
```javascript
var rand = Math.round( Math.random() * 15);

if(rand > 0){
	if(rand % 3 === 0){
		if(rand % 5 === 0){
			alert("fizzbuzz");
		}
		else{
			alert("fizz");
		}
	}
	else if(rand % 5 === 0){
		alert("buzz");
	}
	else{
		console.log(rand);
	}
}
else{
	console.log(rand);
}
```

## Putting it All Together: Control Flow and Comparison Operators
- Create a text adventure game with JavaScript.  You will encounter a zombie, choose a weapon to fight with, and have a 50/50 chance of either defeating the zombie with our weapon or getting bitten and losing the game,
```javascript
alert("It is the zombie apocalypse!  You are looting a store and suddnely a zombie bursts through the door!");

var weapon = prompt("What weapon do you choose to fight the zombie with?  The bow and arrow, the axe or the rubber chicken?");

var rand = Math.round( Math.random());

alert("You attack the zombie with your " + weapon);
if (rand === 1){
	alert("Your attack was successful.  You killed the zombie.");
}
else{
	alert("You didn't aim for the head and the zombie bit you.  GAME OVER.");
}
```