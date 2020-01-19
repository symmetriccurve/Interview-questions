
### What is Async and Await ?
**Await** keyword is valid only inside a Async function. Async is a function and await always followed by a promise.

**Async** and **Await** helps the write the asynchronous programming in synchronous way, for better readability and maintainability. 
We can avoid callbacks and use a await that would return the promise and we can add more awaits to resolve the promises until we have the required format of data(like JSON.)

Example:

```javascript
Async function getData(){
     var response = await fetch(‘https://sampleApi.com/sample')
     var  responseJson = await response.json()
     console.log(responseJson) 
   /*Look how code flows synchronous way but this asynchronous */
}

```

---

### What is scope in javascript ?

---

### What is the difference between map, reduce, filter and forEach in javascript ?

---

### What is call and apply in javascript ?

---

### What is context in javascript ?

---

### What are event bubbling and event capture ?

---

### What are some design pattern you are familiar with ?
https://addyosmani.com/resources/essentialjsdesignpatterns/book/#designpatternsjavascript

1. constructor pattern
2. Modular pattern

3. constructor pattern
Constructor pattern is used if a object method should be shared across multiple objects,
Let's say a Car is a constructor function which create a Car object every time it is called

```javascript
function Car(name, model){ // Construction functions starts with capital letter(Just to differentiate)
  this.name = name;
  this.model = modal;
  this.toString = function(){
    console.log("Name:",this.name,"Model",this.model)
  }
}

To create a new instance of the car object, a `new` keyword is used.
var civic = new Car( "Honda Civic", 2009 );
var mondeo = new Car( "Ford Mondeo", 2010 );

Every time a new car object is created, the function toString is also created which takes memory.

instead a prototype function can be created to share across all the instances of the car objects

function Car(name, model){ // Construction functions starts with capital letter(Just to differentiate)
  this.name = name;
  this.model = modal;
}

Car.prototype.toString = function(){
    console.log("Name:",this.name,"Model",this.model)
  }
```
Above, a single instance of toString() will now be shared between all of the Car objects.

2. 
---

### What is this in a javascript ?

---

### What is the output of the following code and why ?

```javascript

for (i = 1; i <= 5; ++i) {
  setTimeout(function(){
    console.log(i);
  }, 1000);
}
```

[Answer](https://coderwall.com/p/_ppzrw/be-careful-with-settimeout-in-loops)

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

### How do you create classes in Javascript ?

---

### what are different ways you can create objects in javascript ?

---

### Is Javascript object oriented programming language ?

---

### What do you understand by call stack in Javascript ?

---

### What is event loop ?

---

### What is hoisting in javascript ?

---

### What are pure functions ?

A Pure function is function which does not alter any variable values outside
 https://medium.com/@jamesjefferyuk/javascript-what-are-pure-functions-4d4d5392d49c

---

### What is ES6 ? 

https://benmccormick.org/2015/09/14/es5-es6-es2016-es-next-whats-going-on-with-javascript-versioning/

---

### Your Favorite ES6 features ?
### Did you use any ES6 features in your project ?
### Are you aware of any ES6 features ?

I have extensively used many ES6 features in my project.
Few of them are destructuring, block-scoped variables, Arrow functions(also called fat arrow functions), spread operators, StringInterpolation, property Shorthand, ES6 Stateless components for creating react components and default values for function parameters

I would use `destructuring` to parse through a object and assign respective property values as stand alone variable, this is very helpful and cut down few lines of code and very intuitive to read, I combine this with default values assignment just in case if the property does not exist, this one liner creates a property as well as assign a `default value` , I love this.

I use arrow functions to bind the context of the function to the object where the function is executed, I use them a lot to create functions without use of keywords `function` and `return`, It's kinda of confusing to me in the beginning but I slowly learnt the art of using arrow functions

StringInterpolation is another thing I use a lot to concat the strings, after using this feature, I thought why did it take so long for ECMA team to come up with this feature.


Read more here: 

1. http://es6-features.org/#Constants
2. http://es6-features.org/#StringInterpolation
3. https://github.com/lukehoban/es6features

---

### Difference between let and var ?
https://stackoverflow.com/questions/762011/whats-the-difference-between-using-let-and-var-to-declare-a-variable

---

### what is polymorphism and how it is achieved in javascript ?
Polymorphism in Object-Oriented Programming is the ability to create a variable, a function, or an object that has more than one form
