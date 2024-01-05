# Arrow Functions

### **Definition: Arrow functions provide us with another way to define functions. There are some semantic differences between arrow functions and regular functions depending on the context they are being used.**

### Structure/Syntax

```jsx

// Normal Anonymous Function
const sayHello = function(firstName, LastName) {
	console.log(firstName, LastName);
}
// Arrow function syntax
const myFunction = (arg1, arg2) => {
  console.log(arg1, arg2)
}
myFunction(arg1, arg2);

```

- In the above example, the arrow function works as an anonymous function(It's not a standalone function and is assigned to a variable)

### We **cannot** define arrow functions as named standalone functions

Here is a code block example in JavaScript:

```jsx
// Arrow function with implicit return
helloWorld()=> {
	console.log("Hello World");
} // bad (invalid)

// named function
function helloWorld() {
	console.log("Hello World");
} // good (valid)
```

- Because we can’t define them as named standalone functions they can’t be used to define constructor functions

```jsx
// normal constructor function
function Animal(n) {
	this.name = n;
} // valid
cost animal = new Animal("tiger"); 

Animal(n) =>() {
	this.name = nl
} // invalid, not a valid syntax

const Person = (n) => {
	this.name = n;
} // valid syntax but can't be used as a constructor function 
const person = new Person("steph"); // invalid, TypeError Person 
```

- In the above example defining a constructor function using an arrow function in both ways is invalid.
- It's just impossible to create a constructor from an arrow function. At least for now.

If our arrow function only takes in one argument we can do this

```jsx
const addOne = num => num + 1;
// nice and clean
// here naum is the argument, and we return num + 1
// notice
```

- Notice we don’t need a return statement.

### arguments keyword

Unfortunately, arrow functions don’t have access to the arguments keyword like normal anonymous  and standalone functions do

```jsx
function myFunction() {
console.log(arguments);
}
myFunction(5,6,7,8); // outputs [5,6,7,8]

// however
const randomFunction = ()=> {
	console.log(arguments);
}
randomFunction(5,6,7,8); // outputs undefined
```

- In the above example, **arguments is** defined for our regular standalone function and we get an output with the arguments we passed into the function call (5,6,7,8)
- However, for our arrow function randomFunction, we’ll get an error telling us arguments is undefined

### So why use Arrow Functions?

1. They can improve readability and make things look nice if used correctly 

### Arrow Functions and Execution Contexts

When arrow functions are used as an object method, they do not create a binding between the object it's being used in and the arrow function itself,

- in other words, they don’t create their **own execution context** like regular functions do
- Therefore when we use **this** inside the arrow function it won’t point to the object it is inside of
- The value of **This** will depend on the context in the surrounding scope of the object, which could be the Window object, or maybe even another object

```tsx
// an animal object using regular function
const animal = {
	name: "blue whale",
  makeSound(){
		console.log(this.name, " made a sound.")
	},
	age: 50,
}
animal.makeSound(); // Outputs "blue whale made a sound"

// value of this is the animal object in the above case

// an animal object using arrow function
const animal = {
	name: "blue whale",
  makeSound: ()=> console.log(this.name, " made a sound."),
	age: 50,
}
animal.makeSound(); // undefined, field name may not exist in the surrounding scope

// value of this depends on the surrounding scope

```

- in the above code, there's no binding between makeSound and the animal object because we use an arrow function
- therefore **This** will **NOT** point to the animal object
- **This’s** value will depend on the surrounding scope(context) the animal object is defined in

The same concept applies to adding arrow functions to prototypes of objects

Take a look at this

```jsx
const animal = {
    name:"Lion",
    talk() {
        setTimeout(function(){
            console.log(this);
        }, 5000);
    },
}
animal.talk(); // outputs setTimeout function/object
```

The value of **this** in the talk function ****will not be the animal object

Why, the value of **this** will be the setTimeout function (functions are also objects)

In other words, a binding is created between the callback function and the **setTimeout** function/object

However here:

```jsx
const animal = {
    name:"Lion",
    talk() {
        setTimeout(()=> {
            console.log(this.name);
        }, 5000);
    },
}
animal.talk(); //outputs "Lion"
```

- In the above code, the value of this will be the animal object
- why? The surrounding scope **this** is being used in is the animal object
- The immediate context **this** is being used in is the setTimeout function

### In General, to prevent confusion, do not use arrow functions for

1. Object methods
2. Prototypes
3. Constructor (Constructor functions)
4. Event handlers
