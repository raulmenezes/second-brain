---
aliases:
  - encapsulated-objects-can-contain-related-data-and-code
note-type: permanent
tags:
  - area/knowledge
  - area/software-engineering
  - topic/javascript
---

# JavaScript Objects and Prototypes

Reference note on object construction, polymorphism, and the JavaScript prototype chain.

Object data and functions stored in an object package (namespace)  **Polymorphism** Ability of multiple object types to implement the same functionality

**Constructors** Provide the means to create as many objects as you need in an effective way, attaching data and functions to them as required.

In Javascript When a new object instance is created from a constructor function, the functionality is not all copied over Instead the functionality is linked to via a reference chain called a prototype chain   Constructor functions is JavaScript's version of a class 	It basically just defines properties and methods E.g. function Person(name) {
  this.name = name;
  this.greeting = function() {
    console.log(‘Hi! I\'m ' + this.name + '.');
  };
}
 var person1 = new Person('Bob');  new keyword to create a new object Using “this” keyword so the new objects use their own properties  When we are calling our constructor function, we are **defining greeting() every time**, which isn't ideal. To avoid this, we can define functions on the **prototype** instead.  Constructors can help you give your code order you can create constructors in one place, then create instances as needed   Create object instances without first creating constructors create() allows you to create a new object based on any existing object. E.g. 	var person2 = Object.create(person1); It has the same properties and method available to it.  create() actually does is to create a new object from a specified prototype object
 	person2.__proto__ returns person1 object  Prototype property can be used to add methods to existing constructors. Prototype Chain An object's prototype object may also have a prototype object, which it inherits methods and properties from, and so on

![[attachments/screen-shot-2017-11-15-at-14-54-01.png]]

Person() constructor's prototype object is Object

The methods and properties are not copied from one object to another in the prototype chain
E.g. person1 has to walk up the chain to Object to access valueOf() method.

## Related
- [[software-engineering-moc]]
- [[javascript-and-v8-notes]]
- [[frontend-interview-notes]]
- [[elasticsearch]]
