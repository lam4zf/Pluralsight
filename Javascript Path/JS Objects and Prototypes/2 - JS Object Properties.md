## Using Bracket Notation to Access JS Properties
- Using bracket notation lets us access properties whose names would otherwise be invalid identifiers
```javascript
'use strict';

var cat = {
  name: 'Fluffy',
  color: 'White'
}
cat['Eye Color'] = 'Green'
display(cat['Eye Color'])
```

## Using JS Property Descriptors
- Every property has a descriptor that lets us see the attributes of that property.
```javascript
display(Object.getOwnPropertyDescriptor(cat, 'name'))
```

## Using the Writable Attribute
- _Writable_ prevents modifying the value of a property (can't change name after its set)
```javascript
var cat = {
  name: 'Fluffy',
  color: 'White'
}
Object.defineProperty(cat, 'name', {writabe: false})
cat.name = 'Scratchy' //this will cause an error since you cant' change the value now.  needs strict mode on
```
```javascript
var cat = {
  name: {first: 'Fluffy', last: 'LaBeouf'},
  color: 'White'
}
Object.defineProperty(cat, 'name', {writabe: false})
cat.name.first = 'Scratchy' //this will work now since name is just a pointer to another object.  That pointer can't be overridden
```

## Using the Enumeralbe Attribute
- By default, properties on an object are enumerable, meaning you can iterate over them in a loop
```javascript
var cat = {
  name: {first: 'Fluffy', last: 'LaBeouf'},
  color: 'White'
}

Object.defineProperty(cat, 'name', {enumerabe: false})

for (var propertyName){
	display(propertyName + ': ' + cat[propertyName])//name won't be displayed
}

display(JSON.stringify(cat)) //name won't be JSON serialized
```

## Using the Configurable Attribute
- Locks down certain property attributes from being changed and from the property from being deleted
```javascript
var cat = {
  name: {first: 'Fluffy', last: 'LaBeouf'},
  color: 'White'
}

Object.defineProperty(cat, 'name', {configurable: false})
Object.defineProperty(cat, 'name', {enumerable: false}) //throws error
Object.defineProperty(cat, 'name', {configurable: true}) //trhows error
delete cat.name //throws error
```

## Using Getters and Setters
- ALlow you to specify the return value of a property using a function and set the value of a property using a function.
```javascript
var cat = {
  name: {first: 'Fluffy', last: 'LaBeouf'},
  color: 'White'
}

Object.defineProperty(cat, 'fullName',
	{
		get: function(){
			return tuhisname.first + " " + this .name.last
		},
		set: function(value){
			var nameParts = value.split(' ')
			this.name.first = nameParts[0]
			this.name.last = name.Parts[1]
		}
	})
cat.fullName = 'Muffin Top'
display(cat.fullName)
```