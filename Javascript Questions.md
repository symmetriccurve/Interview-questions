
### What is Async and Await ?
Await keyword is valid only inside a Async function. Async is a function and await always followed by a promise.

Async and await helps the write the asynchronous programming in synchronous way, for better readability and maintainability. 
	We can avoid callbacks and use a await that would return the promise and we can add more awaits to resolve the promises until we have the required format of data(like JSON.)

Example:

```javascript
Async function getData(){
     var response = await fetch(‘https://sampleApi.com/sample)
     var  responseJson = await response.json()
     console.log(responseJson) 
   /*Look how code flows synchronous way but this asynchronous */
}

```

---

### What is Dependency Injection ?

---

### What are closures in Javascript ?

A closure is a function inside a function, we use closure to create private variables. Let’s a we create a variable by var a = 10

We can change the variable value from anywhere globally but to avoid exposing variables to global scope, we create closures and have variables inside closures.

The beauty of closure is that the closure can remember the last call value of the function even though the parent function has executed long back.

---

### What do you understand by prototype in Javascript ?

---

### What is the output of // ‘1’ + 2 + 6 = ?
// 1 +3+7 +’10’ = ?
// – ‘Hi’ = ?
// – ‘1’ + 10 = ? and why ?

---

### How do you create classes in Javascript  ?

---

### Is Javascript object oriented programming language ?

---

### What do you understand by call stack in Javascript ?

---

### What is event loop ?

---

### What are pure functions ?

A Pure function is function which does not alter any variable values outside
 https://medium.com/@jamesjefferyuk/javascript-what-are-pure-functions-4d4d5392d49c

---

### What is ES6 ? 

https://benmccormick.org/2015/09/14/es5-es6-es2016-es-next-whats-going-on-with-javascript-versioning/

---

### Your Favorite ES6 functions ?
http://es6-features.org/#Constants
http://es6-features.org/#StringInterpolation
http://es6-features.org/#ExpressionBodies
https://github.com/lukehoban/es6features

---

### Difference between let and var ?
https://stackoverflow.com/questions/762011/whats-the-difference-between-using-let-and-var-to-declare-a-variable
