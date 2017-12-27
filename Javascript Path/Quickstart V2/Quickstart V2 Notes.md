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
	default: alert("Please enter 'sagitarius', 'gemini', or 'taurus'.); break;
}
```