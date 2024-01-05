# JavaScript

# Synchronous JavaScript

- Code is executed in the order it was setup
- Step by Step execution
- one line of code will block next line until current line finishes

# Asynchronous JavaScript

Definition: Asynchronous programming allows us to execute code out of order. We can perform operations independent of the main program flow. 

- setTimeOut(() ⇒ {}, time): Async function, executes code in the future
- Asynchronous tasks separate from the normal synchronized tasks
- Asynchronous tasks start their processes while the main processes run
- The main processes and other processes are asynchronous (separate, and don’t depend on each other)
- Callback functions are functions passed to other functions as arguments
- Asynchronous Callback functions: these callback functions are executed after our asynchronous operation is complete, so at some point later in time
- Synchronous Callback functions: These functions are executed synchronously with the other code in our program (immediately)

# Promises

### Promise:

Definition: In JavaScript,  a promise is an object. There are two sides to a promise.

1. The Promise Maker: The API or person that makes the promise object and returns it
2. The Promise Receiver: The person who fetches data from the API and receives the promise

There are three states for a promise:

1. pending: our asynchronous function is still working and hasn’t fulfilled our rejected the promise
2. fulfilled: The asynchronous function successfully worked and has fulfilled our promise, returning any data along with it
3. rejected: The asynchronous function failed to perform some operations and returns a failed or rejected promise

A promise is an object that takes in a function as an argument, with two parameters that are also functions

1. resolve: If everything goes well, call resolve with whatever we want to return
2. reject: if something doesn’t work out, call reject with an error message or null or something

```jsx
// creating a promise
let promise = new Promise((resolve, reject) => {
if (data available)
	resolve(data);
else
	reject("No data available");
});
```

- Promises are usually returned from an API. If we attempt to fetch data from an API. We can utilize that data to perform one operation or multiple operations with it.
- If we want to do multiple things we can utilize promise chaining

```jsx
// promise chaining
let response = promise
.then(func1)
.then(func2)
.then...
.catch((error) => {console.log(`error code: ${error}`)})
.finally(() => {console.log("finally finished")})
```

- If the promise is fulfilled, our functions func1 and func2 will successfully be called, and manipulate the data returned in some way. And our finally block will also be executed
- If something goes wrong and the promise is rejected, our catch block will catch the error, and do something

# Async/Await

- Every asynchronous function returns a promise

```jsx
async function getData() {
	return "Data";
}
// returns Promise {"Data"}

```

- Async/Await is an alternative to using promise chaining
- It is more readable and looks nicer
- Most of the time async and await must be used together

```jsx
// example of an async function
async function getData() {
    try {
        let response = await fetch('<https://api.example.com/data>');
        let data = await response.json();
        console.log(data);
    } catch (error) {
        console.log('Error:', error);
    }
}

```

[Prototypes & Inheritance](https://www.notion.so/Prototypes-Inheritance-6d3637eb1c2a4e2597018de4d0df3bbe?pvs=21)

[The This Keyword](https://www.notion.so/The-This-Keyword-dc1217d2144a49138426ea36f069709a?pvs=21)

[Arrow Functions](https://www.notion.so/Arrow-Functions-06a3b4f3c7a3478aa12529e18923628b?pvs=21)
