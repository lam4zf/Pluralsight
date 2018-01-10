## Intro to Project
- This course will cover objects.

## Lesson 1: Objects
- An _object_ is a collection of _properties_, which are described in the form of _key/value_ paris.  We can use objects to model "things" using code.
- An object for coffee looks like this:
```javascript
var myCoffee = {
	flavor: "espresso",
	temperature: "Hot",
	ounces: 32,
	milk: false
};

console.log(myCoffee.ounces);
```

## Lesson 2: Methods
- When an object has a property with a funciton as the value, it is referred to as a _method_ of that object.
```javascript
var myCoffee = {
	flavor: "espresso",
	temperature: "Hot",
	ounces: 32,
	milk: false,

	reheat: function(){
		if(this.temperature != "Hot"){
			this.temperature = "Hot";
			console.log("Coffee has been set to " this.temperature);
		}
	}
};
myCoffee.temperature = "cold";
console.log("The coffee is " myCoffee.temperature);
myCoffee.reheat();
```