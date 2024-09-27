# JavaScript Functions 

## 1. Named Functions
A named function is a traditional function with a name that can be called and referenced within its scope.

```javascript
function add(a, b) {
    return a + b;
}

console.log(add(3, 5));  // Outputs: 8
```
## Explanation
- The function add is declared with the function keyword and has the name add.
- It can be called by using its name and passing arguments.
- Named functions are reusable and easy to reference throughout the code.


## 2. Anonymous Functions
An anonymous function is a function without a name, often assigned to a variable or used as an argument to another function.
```javascript
const multiply = function(a, b) {
    return a * b;
};

console.log(multiply(3, 5));  // Outputs: 15
```
## Explanation
- The function has no name and is assigned to the variable multiply.
- It behaves like any other function and can be called using the variable it’s assigned to.
- Anonymous functions are often used for short-lived purposes, such as in callbacks.

## 3. Arrow Functions
Arrow functions provide a shorter syntax for writing functions. They are anonymous by default and do not have their own this context.
```javascript
const subtract = (a, b) => a - b;

console.log(subtract(10, 4));  // Outputs: 6
```
## Explanation
- Arrow functions use the => syntax instead of the function keyword.
- When the function body contains a single expression, the result is returned implicitly without using the return keyword.
- Arrow functions do not bind their own this, making them suitable for certain functional programming tasks.


## 4. Immediately Invoked Function Expression (IIFE)
An IIFE is a function that is executed immediately after it is defined.
```javascript
(function() {
    console.log("I am an IIFE!");
})();
```
## Explanation
- The function is enclosed in parentheses () to create an expression.
- The trailing () immediately invokes the function.
- IIFEs are useful for avoiding polluting the global scope and are often used in modular patterns.

## 5. Higher-Order Functions
A higher-order function is a function that takes another function as an argument or returns a function as its result.
```javascript
function greet() {
    console.log("Hello!");
}

function higherOrderFunction(callback) {
    console.log("Before calling callback");
    callback();
    console.log("After calling callback");
}

higherOrderFunction(greet);
```
## Explanation
- higherOrderFunction takes greet as an argument and calls it as a callback.
- Higher-order functions allow more abstraction and are widely used in functional programming, such as with map, filter, and reduce.


## 6. Callback Functions
A callback function is a function passed as an argument to another function and is executed later in response to an event or condition.
```javascript
function fetchData(callback) {
    setTimeout(() => {
        console.log("Fetching data...");
        callback();
    }, 1000);
}

fetchData(() => {
    console.log("Data fetched!");
});
```
## Explanation
- fetchData simulates an asynchronous operation (using setTimeout) and calls the provided callback once the operation is done.
- Callbacks are used extensively in asynchronous programming to handle operations like API calls or I/O.


## 7. Generator Functions
A generator function is a special kind of function that can pause its execution and yield multiple values over time, returning an iterator.
```javascript
function* generateSequence() {
    yield 1;
    yield 2;
    yield 3;
}

const generator = generateSequence();

console.log(generator.next().value);  // Outputs: 1
console.log(generator.next().value);  // Outputs: 2
console.log(generator.next().value);  // Outputs: 3
```
## Explanation
- The * indicates that this is a generator function.
- The yield keyword allows the function to pause execution and return a value.
- Generators are useful for creating sequences of values and implementing iterators.

## 7. Async Functions
An async function allows asynchronous operations to be written in a more readable manner using async and await.
```javascript
async function fetchData() {
    const response = await fetch('https://jsonplaceholder.typicode.com/posts');
    const data = await response.json();
    console.log(data);
}

fetchData();
```
## Explanation
- async functions always return a Promise.
- The await keyword pauses the function execution until the promise is resolved, making asynchronous code appear synchronous and easier to read.
- async/await helps avoid "callback hell" and provides better error handling with try/catch blocks.
