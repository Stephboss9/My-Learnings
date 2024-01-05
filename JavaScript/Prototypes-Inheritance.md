# Prototypes & Inheritance

### What is Inheritance?

In JavaScript, inheritance refers to the ability to share properties across multiple defined objects or instances of classes. An object inherits its properties which could include functions or fields from its prototype.

### Prototypal Inheritance:

Every object has a field __**proto__** 

- This field is an object itself and provides the blueprint for that object, listing what properties it has
- These properties could include functions, regular primitive fields, or more objects
- If our object is an instance of a class then the __**proto__** field will equal the **prototype** field of the class. Both fields define the class/blueprint.
- Its possible to manipulate the __**proto__ field of an object to define a new property (function, field, another object).**
- This newly added property will be universal to all other objects of the same kind
- In other words all other instances of the same kind of object will **Inherit** the newly added field

```jsx
// let animal be an object
function Animal() = {
	this.roar = function() {
		console.log("ROOOAR");
  }
}

let dog = new Animal();
// add new field to the definition of object
dog.__proto__.age = 50; // same as Animal.prototype.age = 50; since they're equal

```

- In the above example, age is added as a new field to the __**proto__** field of dog
- This will add it to the prototype of Animal
- So all other instances of Animal will also have the field age
- In the above example, the function roar will be available to every instance of Animal
- However, if we want to change the function roar, we will have to change it for all instances
- This is because each instance of animal will have its own roar function. It's not shared for all instances.
- if we did something like…

```jsx
Animal.prototype.roar = function() {
	console.log("new and improved roar");
}
```

Every instance of Animal will now have this new and updated roar function

Here are some different ways to define an object

```jsx
// let Animal be our blue print for an instance of an object
function Animal() = {
	this.roar = function() {
		console.log("ROOOAR");
  }
}
// 1st way
let dog = new Animal();
// 2nd way
let cat = Object.create(Animal);
// 3rd wat
let unknownObject = {};
Object.setPrototypeOf(unknownObject, Animal);
// add a new field to the prototype of an object
dog.__proto__.age = 50; // same as Animal.prototype.age = 50; since they're equal

```
