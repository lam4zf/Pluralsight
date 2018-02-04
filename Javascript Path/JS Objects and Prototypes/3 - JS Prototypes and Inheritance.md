## Getting Started with JS Prototypes
- Imagine you have an array, and want to access the last property in the array.  Array's don't have a _last_ property, but since JS is dynamic, we can add our own.
```javascript
var arr = ['red', 'blue', 'green']

Object.defineProperty(Array.prototype, 'last', {get: function(){
	return this[this.length-1]
	}})

var arr2 ['one','two','three']
display(arr.last)
display(arr2.last)
```

## What is a Prototype?
- A prototype is an object that exists on every funtion in JS.  Objects do not have a prototype property, but they do have a _proto_ property.
- A _function's prototype_ is the object _instance_ that will become the prototype for all objects created using this function as a constructor
- An _object's prototype_ is the object _instance_ from which the object is inherited.

```javascript
function Cat(name, color){
	this.name = name
	this.color = color
}
var fluffy = new Cat('Fluffy', 'White')
display(Cat.prototype)
display(fluffy.__proto__)

Cat.prototype.age = 3

display(Cat.prototype)
display(fluffy.__proto__)

var muffin = new Cat('Muffin', 'Brown')

display(muffin.__proto__)
```

## Instance vs Prototype Properties
```javascript
function Cat(name, color){
	this.name = name
	this.color = color
}
Cat.prototype.age = 3

var fluffy = new Cat('Fluffy', 'White')
var muffin = new Cat('Muffin', 'Brown') // both cats have an age of 3

Cat.prototype.age = 4 // both cats have an age of 4
fluffy.age = 5 // fluffy has an age of 5, muffin still 4.  A new property was added to the object, __proto__ is stil 4

```

## A Graphical Overview of Prototypes
https://cl.ly/431C373O1u1e
- If an object does not have a property, it checks the object's prototype for that property

## Changing a Function's Prototype
- Prototypes are objects that live in memory.
```javascript
function Cat(name, color){
	this.name = name
	this.color = color
}
Cat.prototype.age = 4

var fluffy = new Cat('Fluffy', 'White')
var muffin = new Cat('Muffin', 'Brown') // both cats have an age of 4

Cat.prototype.age = { age: 5 } // both cats still have an age of 4. setting to new object
var snowbell = new Cat('Snow', 'White') //snowbell has an age of 5, others still 4
```

## Multiple Levels of Inheritance
- Each __proto__ has a prototype that eventually resolves to null.
```javascript
function Cat(name, color){
	this.name = name
	this.color = color
}
Cat.prototype.age = 4

var fluffy = new Cat('Fluffy', 'White')
display(fluffy.__proto__) //cat with age 4
display(fluffy.__proto__.__proto__) //Object
display(fluffy.__proto__.__proto__.__proto__) //null
```

## Creating Your Own Prototypal Inhericance Chains

```javascript
function Animal(voice){
	this.voice = voice || "grunt"
}
Animal.prototype.speak = function(){
	display(this.voice)
}

function Cat(name, color){
	Animal.call(this, "Meow") //any animal related initialization can occur
	this.name = name
	this.color = color
}
Cat.prototype = Object.create(Animal.prototype)  //doesn't use new so we don't call teh Animal function
Cat.prototype.constructor = Cat

var fluffy = new Cat('fluffy','white')
fluffy.speak()
```

## Creating Prototypes with 
- Not enumerable by default
```javascript

class Animal {
	constructor(voice){
		this.voice = voice || "grunt"
	}

	speak(){
		display(this.voice)
	}
}

class Cat extends Animal{
	constructor(name, color){
		super('Meow')
		thisname = name
		this.color = color
	}
}

var fluffy = new Cat('fluffy','white')

```