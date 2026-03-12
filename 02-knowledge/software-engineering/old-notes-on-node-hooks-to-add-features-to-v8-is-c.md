---
tags:
  - area/knowledge
  - area/software-engineering
  - topic/javascript
---

# OLD NOTES ON NODE  Hooks to add features to   V8 is C++

V8 allows me to write my own C++ code to make available to javascript

Something new in Javascript -> triggers code in C++ to run  Thus adding features to Javascript
Powerful as C++ has more features than Javascript

Commonjs Modules - an agreed upon standard for how code modules should be structured

Object - collection of Name/value pair

Prototypal inheritance and function constructors

Inheritance
One Object gets access to the properties and methods of another object

Function constructors
Normal function that is used to construct objects

New will execute the function

function Person(firstname, lastname) {
	this.firstname = firstname
	this.lastname = lastname
}

var john = new Person(‘John’, ‘Doe’)

Prototype - properties available to all objects
__proto__

Primitive: type of data that represents a single value

Objects pass by reference instead of pass by value. Pointing to the same place in memory

Immediately invoked function expressions (IFFE)

model.exports is what the require function returns 

Module pattern

## Related
- [[software-engineering-moc]]
- [[new-notes-from-handbook-https-medium-freecodecamp-org-the-definitive]]
- [[code-quality-see-how-code-has-affected-the-service]]
- [[es6-new-features]]
