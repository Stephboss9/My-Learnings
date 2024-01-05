# The This Keyword

## What is the “This” Keyword?

Definition: 

The **this** keyword is literally refers to the object in the context that it is inside of

It is used a lot in classes to refer to the methods and fields belonging to that class

In our browser, or in global scope, the **this** keyword is the window object

So we can access the fields and methods of the window object doing

- window.aField or
- this.aField

 The value of **this** (an object) is going to depend on the context in which it is being used

For example …

```jsx
// say we define a function 
function eat() {
   console.log(`${this.name} ate pizza`);
}
// and we define two objects
let stephane = {"name": "Stephane", "eatFood":eat};
let bob = {"name":"bob", "eatFood":eat};

stephane.eatFood(); // this will print "stephane ate pizza"
bob.eatFood(); // this will print "bob ate pizza"
```

In the above example, we define two objects with name field and a eatFood function

When we call stephane.eatFood, it called our eat function we defined

- In this case, the **this** keyword will point our stephane object because that's the context it's being used in
- and so we can use the dot operator to get the name field of the stephane object using **this**, because **this** is the **stephane object**
