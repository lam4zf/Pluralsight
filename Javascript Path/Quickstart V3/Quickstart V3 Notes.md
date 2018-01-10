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

## Lesson 3: Object literals and constructors
- When we created our myCoffee object, we created it using what is called an _object literal_.  WHen we create objects this way, we are both defining and creating a single object, referred to as an _instance_ of an object.
- Use a _constructor_ to create multiple instances of an object.  Each instance _inherits_ the properties and methods of its constructor.
```javascript
function Coffee(flavor, temp, size, milk){
	this.flavor = flavor;
	this.temperature = temp;
	this.size = size;
	this.milk = milk;
}

var coff = new Coffee("Columbian", "Hot", "Venti", false);

console.log(coff.flavor);
```

## Lesson 4: OOP
- Constructor = prototype
- Host Objects: objects defined by the enviroment in which code is run.  A browser is an exmple of a host enviroment and gives us _Document, Window, Element, Event. Node, Comment, Console, etc_
- Core Objects: defined by and built into JS itself: _Math, Object, String, Boolean, Array, Date, Number, etc_
- Everything else is written by us

## Lesson 5: This and the Global Object
- JS uses _objects_ as a way of passing around and sharing code.
- When we create variables, fucntions and objects, they are properties of the _global object_.
- The _window_ is the _global object_ when the host environment is the web.
```javascript
alert(this); //alerts [object window]

function sayHello(){
	alert("Hello");
}
window.sayHello(); //also works

function alert(){
	console.log("Hello!"); //overrides default "alert()" function
}
```

## Lesson 6: Local and Global Scope
- All code written up to this point has been _global_ in _scope_, so anything can access it and change it.
- Variables inside a funciton are _local_ in _scope_.  You need to use the _var_ keyword though here to keep it local.