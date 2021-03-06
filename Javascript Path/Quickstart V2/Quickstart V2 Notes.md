## Intro to Project
- This course will cover topics like switch statements, loops, arrays, functions

## Lesson 1: Control Flow via Switch Statements
- Another way of writing code in a non-linear way is by using a *switch statement*.
```javascript
var sign = prompt("What is your astrological sign?").toLowerCase();

switch(sign){
	case "sagitarius": alert("today will be a good day."); break;
	case "gemini": alert("second case"); break;
	case "taurus": alert("today will be a not so good day."); break;
	default: alert("Please enter 'sagitarius', 'gemini', or 'taurus'."); break;
}
```

## Lesson 2: For Loops
- *Loops* are another form of control flow.  They "loop" throuhg a block of code until an original specified condition is no longer true.
```javascript
for (var i = 0; i < 11; i++){
	console.log(i);
}
```

## Lesson 3: Fizzbuzz Revisited
- The real problem: Print all numbers from 1 to 100 with three exceptions:
	- If the number is divisible by 3, print fizz
	- If the number is divisible by 5, print buzz
	- If the number is divisible by both 3 and 5, print fizzbuzz

```javascript
//cleaner solution with if/else
for (var i = 1; i <= 100; i++){
	var output = "";
	if(i%3)
		output += "Fizz";
	if(i%5)
		output += "Buzz";

	console.log(output||i); //if output is empty, output evaluates to false and i is logged
}

//uglier solution with switch
for (var i = 1; i <= 100; i++){
	switch(true){ //need a true in there since just "i" will always send to default
		case(i % 3 == 0 && i % 5 == 0): console.log("fizzbuzz"); break;
		case(i % 3 == 0): console.log("fizz"); break;
		case(i % 5 == 0): console.log("buzz"); break;
		default: console.log(i); 
	}
}
```

## Lesson 4: While Loops
- `do..while` loops execute once and continues as long as the specified condition is still true.
- use when you don't know how many times something should run
- `do..while` will always run at least once as opposed to `while`
```javascript
var i = 0;
do {
	console.log(i)
	i++;
} while(i < 11);

i = 0;
while (i < 11){
	console.log(i);
	i++;
}
```

## Lesson 5: Functions
- *Functions* allow us to associate a command with an action, making messy code cleaner and reusable.
- When you call a function, the information you pass to the function is called an *argument*.
```javascript
function sayHello(name){
	console.log("Oh hi " + name);
}

sayHello("Mark");
sayHello("Lisa");
```

## Lesson 6: Arrays
```javascript
var friends["Mark", "Lisa", "Denny"];
console.log(friends[0]); //"Mark"

friends[3] = "Bob"; //adds a new name at index 3

friends.push("Mary"); //if you don't know the index, this will add it to the end
```

```javascript
var friends["Mark", "Lisa", "Denny", "Peter", "Steven", "Claudette"];
function sayHello(name){
	console.log("Oh hi " + name);
}

for(i = 0; i < friends.length; i++){
	sayHello(friends[i]);
}
```

## Lesson 7: Making JS Files From Scratch
- Make a `scripts` folder in your web project.
- Save a `.js` file inside of it.
- Add it right before the closing body tag, `</body>`.  This helps the page load faster and will let the content render first if there are any errors in the script.
	- `<script src="scripts/main.js" type="text/javascript"></script>`