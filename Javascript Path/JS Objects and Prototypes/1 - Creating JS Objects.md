## Using Object Literals to Create JS Objects
```javascript
'use strict';
```
- This causes javascript to throw errors where it otherwise would silently fail.
- It also disallows using depricated parts of JS.
- Making objects is very easy with literals
```javascript
'use strict';

var cat = {name: 'Fluffy', color: 'White'}

display(cat.name)
```

## The Dynamic Nature of JS
- Really easy to dynamically change objects
```javascript
'use strict';

var cat = {name: 'Fluffy', color: 'White'}
cat.age = 3
cat.speak = function() {display("Meow")}
display(cat.name)
display(cat.age)
cat.speak()
```

## Using Constructor Functions
- What if we want to create multiple instances with the same structure?  JS doesn't have class like static languages, but they allow you to accomplish the same thing.
- Use the _new_ keyword
```javascript
'use strict';

function Cat(name, color){
  this.name = name
  this.color = color
}

var cat = new Cat('Fluffy', 'White');

display(cat)
```
- _this_ refers to a new empty object in this scenario

## Using Object.create() to Create JS Objects
- Everything so far has been "syntactic sugar" for _Object.create()_
```javascript
var cat = Object.create(Object.prototype,
  {
    name: {
      value: 'Fluffy',
      enumeralbe:true,
      writable:true,
      configurable:true
    },
    color:{
      value:'White',
      enumeralbe:true,
      writable:true,
      configurable:true
    }
  })
 ```

## Using ECMAScript 6 Classes
- You can also use the _class_ keyword which is just "syntactic sugar" again for doing the same thing as above.
```javascript
class Cat {
	constructor(name, color){
		this.name = name
		this.color = color
	}

	speak(){
		display("Meooow")
	}
}

var cat = new Cat('Fluffy','White')

display(cat)
cat.speak()
```