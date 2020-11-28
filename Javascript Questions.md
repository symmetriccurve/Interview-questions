### Can you implement promise.race function ? (paypal)

This question is little tricky and needs thorough understanding of how promises work in javascript.
The idea of promise.race is as simple as it sounds, it takes array of promises and puts race to all the promises and which ever wins the race will give the promise response first.

A simple example can be:
imagine if you are trying to make a google search, now google being such a huge company will have may data centers around your location, one might be right next door or may be down the city. Google tries it's best to get the results as quick as possible..we might think getting the results from next door server is much faster then down the city server but what if the data connection to the next door is too slow.. so the browser smartly makes the request to both servers and which ever get you the results first it will consider and drop the request of the next server middle way. Similarly, promise.race([nextDoor, downTheCity]) takes two API calls(calling API is asynchronous so does the promises) and only resolve value from fastest response.

```javascript
promise.race([nextDoor, downTheCity]).then(function (resultsFromFasterServer) {
  showResults(resultsFromFasterServer);
});
```

Instead of using the out of box promise.race, interviewers is asking to implement the same without using promise.race function. we can do something like below which does the same job.

```javascript
function resolvePromises(promises) {
  return new Promise((parentResolve, reject) => {
    promises.forEach((promise) =>
      rule.then((promiseResponse) => parentResolve(promiseResponse))
    );
  });
}

const promises = [
  new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("first");
    }, 500);
  }),

  new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("second");
    }, 300);
  }),

  new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("third");
    }, 400);
  }),

  new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("fourth");
    }, 600);
  }),
];

resolveRules(rules).then((res) => console.log(res));
```

in the above example, promises is a array of promises, each promise takes different time to resolve, think of them as different data centers responding to the request.

Now we take in the promises array into resolvePromises function, and here is where the magic happens. Please follow closely.

First, we take all the promises and loop over(using forEach) the promises to get the response, we wrap all the promises inside an another high level parent promise, and let the child promises resolve one after other, which ever child is resolved first will notify the parent promise saying, `hey I got the data` by calling the parentResolve first.

To give you a more mental modal, think of swimming lanes and each swimmer is a promise and a coach sitting watching over the race, the coach gives a whistle(parentResolve callback) to each swimmer(each promise) and ask to blow the whistle who ever crosses the finish line, the coach(parent promise) just listens to the whistle and stops the race immediately(early terminating the race by saving energy of other swimmers aka saving resources on the client machine to not wait for other request to complete)

This might take a little while to sync in if you are new to promises

---

### What is Async and Await ?

javascript is single threaded programming language and it utmost important to not block the single thread available so we make use of promises in combinations of callback functions to execute asynchronous flow.

promise.

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

##### Javascript

---

### What is the difference between map, reduce, filter and forEach in javascript ?

##### Javascript

---

### What is call and apply in javascript ?

##### Javascript

---

### What is context in javascript ?

##### Javascript

---

### What are event bubbling and event capture ?

##### Javascript

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

##### Javascript

---

### What is this in a javascript ?

##### Javascript

---

### What is the output of the following code and why ?

```javascript
for (i = 1; i <= 5; ++i) {
  setTimeout(function () {
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

##### Javascript

---

### What do you understand by prototype in Javascript ?

##### Javascript

---

### What is the output of // ‘1’ + 2 + 6 = ?

// 1 +3+7 +’10’ = ?
// – ‘Hi’ = ?
// – ‘1’ + 10 = ? and why ?

##### Javascript

---

### How do you create classes in Javascript ?

##### Javascript

---

### what are different ways you can create objects in javascript ?

##### Javascript

---

### Is Javascript object oriented programming language ?

##### Javascript

---

### What do you understand by call stack in Javascript ?

##### Javascript

---

### What is event loop ?

##### Javascript

---

### What is hoisting in javascript ?

##### Javascript

---

### What are pure functions ?

A Pure function is function which does not alter any variable values outside
https://medium.com/@jamesjefferyuk/javascript-what-are-pure-functions-4d4d5392d49c

##### Javascript

---

### What is ES6 ?

https://benmccormick.org/2015/09/14/es5-es6-es2016-es-next-whats-going-on-with-javascript-versioning/

##### Javascript

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

##### Javascript

---

### Difference between let and var ?

https://stackoverflow.com/questions/762011/whats-the-difference-between-using-let-and-var-to-declare-a-variable

##### Javascript

---

### what is polymorphism and how it is achieved in javascript ?

Polymorphism in Object-Oriented Programming is the ability to create a variable, a function, or an object that has more than one form

##### Javascript
