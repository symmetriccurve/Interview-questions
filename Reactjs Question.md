
# This page is constantly updated with new questions and answers(with better examples). Please check back if you are unable find an answer to a existing question or you can submit a new question [here](https://github.com/symmetriccurve/Interview-questions/issues/new)

---

### What do you understand by Component Life Cycle in React OR Explain Component Life Cycle in React ?
Every component in react undergoes three phases, 
Initialization phase, updating phase, unmounting phase.

___On INITIALIZATION PHASE we have:___

```javascript
Constructor  //Using ES6 Syntax
getInitialState // Using ES5 Syntax
```
Both of this methods sets the initial state of the component, [Read more](https://stackoverflow.com/a/30668609)

```javascript
[ComponentWillMount]
```

_This is a depricated component life cycle and this is replaced with **getDerivedStateFromProps**_
We use this to update the state even before UI Elements shows up on DOM
 
```javascript
Render
```

The return of this function is what is seen on the UI, it returns Views wrapped inside a single div( Follow up Question: What do you mean by single div, can we not return multiple divs, go to (1A) )

On the ___UPDATING PHASE___ we have:

```javascript
ComponentWillReceiveProps
```

_This is a depricated component life cycle and this is replaced with **getDerivedStateFromProps**_
Everytime a component receives new set of props, this component life cycle is triggered with a argument which are new set of props

```javascript
getDerivedStateFromProps
```

This component life cycle is the new addition **React 16.3**, this behaves a as combination of componentWillMount and ComponentWillReceiveProps, means this component life cycle is trigger both on the initial render and subsequent renders

```javascript
ShouldComponentUpdate
```

This component life cycle when used appropriately will avoid any unnecessary renders of the component(Follow up Question: What do you mean by unnecessary renders), depending on the business logic it might return true or false, if it returns true a render will be triggered, if not render is avoided.

```javascript
ComponentWillUpdate
```
_This is a depricated component life cycle_ .
If ShouldComponentUpdate returns _true_ componentWillUpdate is triggered

```javascript
ComponentDidUpdate
```

ComponentDidUpdate is called after the Render

___On the UNMOUNTING PHASE___ we have:

``` javascript
ComponentWillUnmount
```

Is called when component is about to be unmounted from DOM


``` javascript
ComponentDidCatch()
```

This is a interesting component life cycle and is only triggered if the component fails to render and showing a fallback ui.

---

### What is a State in a React ?

A state is nothing but a javascript object to determine the behaviour of the component, every time a state change happen in fact a prop change happen, a render is triggered or UI is re-rendered. 

Creating a state 

```javascript
constructor(){
  super()
  this.state = {
	//state goes here
   }
 }
```

---

### Why to use React if there are so many frameworks available in the market ?

React has mechanism called a Virtual DOM which can optimize the mutations on the real DOM, this adds the benefits of faster renders and also react supports  Hot-reloading where you can see the changes on the UI as you change through the Code, most of all it is backed by Facebook with huge community support, Also react can help a web developer to be a mobile developer and vice versa as react shares same language JSX. Its called React-Native

React makes writing Views Easier and Its component Based model helps to debug and Isolate the issues from data and views, and it’s extremely efficient because of virtual DOM.
https://blog.syncano.io/reactjs-reasons-why-part-1/

---

### How different is componentWillMount Vs ComponentDidMount ? (M)
componentWillMount is called before the render is called and ComponentDidMount is called after the render.

---

### What are the life cycle methods that are called on first render ?

Constructor 
ComponentWillMount
Render
ComponentDidMount

---

### I would like to add a listener to my react component that will update the state whenever a event is emitted ? How do you add it ?
I would add the listener in componentDidMount and remove the listener in ComponentWillUnmount. We have to make sure to remove the listener in  ComponentWillUnmount as you say we are updating the state, updating a state on a un mounted component will show a error message 

---

### Which life cycle method do you prefer to make a network call ?(M)

ComponentDidMount()
https://stackoverflow.com/questions/41612200/in-react-js-should-i-make-my-initial-network-request-in-componentwillmount-or-co

---

### Which component life cycle is called when Component receive new Props ?

ComponentWillReceiveProps()

---

### How to Optimize renders in React ?(M)

It;s know that every time a prop is changed or state is changed inside the component a render method is triggered. ShouldComponentUpdate is LifeCycle method that can be logically used to manage the render cycles, this method can return a true or false logically to avoid a re-render.

---

### Do you know any other Libraries like React ?(React is a View Library so there are many. .)

https://github.com/infernojs/inferno
http://riotjs.com/

---

### I have Project A , Project B and Project C. I ask you to develop a reusable component to use across all my projects, and I use different styles in three different projects. How will you manage that inside your component ?

I will allow a style prop to pass into the component, internally I will get the style object you passed into( As you know what styles you need to apply based on the project) and apply to my component. I will add in a default style to component and add a additional check is the style object is passed or not into the component, if not a default style will be applied. I can also parse through the style object you passed from defaultProps and validate for any missing css properties and through you a error or warning depending on how important is the style property.


I have login page on which I have a userId textbox and Password textbox and a SignIn button, next to the Password textbox there is a small Eye icon on which if a user click it will show the password as normal text instead of dot or stars etc. How will you able to do this ?

I will have a state variable called showPassword, which is initially set to false. And on the render function on the Input of the password field on type Property I will throw in a ternary operator if showPassword true then return text if not password. and when user clicks on the eye icon, on every click I will negate the showPassword boolean value and also I will also use the same state variable to switch between open eye icon when password is visible and close eye icon when password is hidden.


When would you use a Class Component over a Functional Component(Stateless Component)?(M)
If I need a state I would use a class component if not If the component solely depends on props passed into it I would use a functional component or ES6 stateless component.

---

### What are keys in React?
Keys in keys are especially used when mapping over a array to generate views, it would help the Virtual Dom to relocate this Children in the Real DOm and add changes/modification/mutations exactly. 

---

### Can we not Mutate the state directly by saying this.state.variable = value ?
A state can only happen through setState because it chains other set states previously called so that the state is mutated once at a time.
To know is the setState happen, we can pass in a second argument inside the setState kinda callback which is called only after the setState is called.

---

### What are the some of the disadvantage of React ?
React is just a view library unlike other UI frameworks , and its JSx syntax which is harder to understand for beginners but will be fun when you get the understanding. 

---

### Difference between React and Angular ? (M)
https://www.codementor.io/chrisharrington/react-vs-angularjs-how-the-two-compare-8t6f1ioan
On a Higher level, React is only View where has Angular is MVC

---

### Can be Props be mutated in React? If not Why ??
Props are immutable 
Props are the data that are passed into the component from the parent component, the only source of truth should be parent.
If it is required to mutate the props, pass a function to mutate the data in the parent component to the child as prop and let the mutation happen in the parent.

https://stackoverflow.com/questions/27643504/react-js-warning-dont-set-the-props-property-of-the-component-mutate-the-exis

---
### How to pass the data from child back to parent ?
Data is passed from child to parent through callback functions.
Similiar to passing the props from the parent to child, a function is passed as prop to the child and child triggers the function with arguments which are passed to the parent

```javascript
//in parent

functionToBePassedAsPropToChild(dataFromTheChild){
 console.log(dataFromTheChild) //'This is data from the child'
}

render(){
  return (
    <Child functionFromParent={(dataFromTheChild)=>functionToBePassedAsPropToChild(dataFromTheChild)} />
  )
}

```

Calling the function from the child which is a prop

```javascript
//in child

handleButtonClickOnChild(){
  const dataTobePassedToParent = 'This is data from the child'
  this.props.functionFromParent(dataTobePassedToParent)
}
```
---

### Can we pass a react component as props to child react component?

React component can be passed by wrapping inside a parent component and within the child component that can access as this.props.children
https://mxstbr.blog/2017/02/react-children-deepdive/

---

### What are refs in React ?
Every Component  in React can be given a ref on the view inside the render/ This is how we can  directly access the DOM element of the React Component. 
The interesting part here is it carries all the user defined functions inside the React Component 

---

### What are Higher order Components in React ?

https://medium.com/@franleplant/react-higher-order-components-in-depth-cf9032ee6c3e

Other places to look 
https://tylermcginnis.com/react-interview-questions/
https://www.toptal.com/react/interview-questions
https://www.codementor.io/blog/5-essential-reactjs-interview-questions-du1084ym1

---

### Can we do a React Application without Redux ?

Absolutely Yes, Redux just a  state management library. We can use a high order component to manage the state.
https://medium.com/@dan_abramov/you-might-not-need-redux-be46360cf367

---

### Can you explain Redux on a Higher Level ?

When an Action is trigger by user interaction of network call or if by business logic, the Action carries optional payload and a action type which intern listened by all the reducers and a reducer having a corresponding action type creates a new state and returns.

This updates the store with new state, and within the component. Redux is connected to Redux using Connect method from React-redux. There are two method associated or that are triggered when a store change happen. MapDispatchToProps and MapPropsToStates .MapPropsToStates pushes the new props and vire is updated accordingly.

---

### What are the methods that connect the redux store and actions to the component ?
MapDispatchToProps and MapPropsToStates

---

### How Does Redux help in State management ? 

 If you have a application whose components are nested heavily, it requires a lot of callback  functions and props to be passed from parent to child so on and so forth. At a point it would be hard to determine the state of the application as it is combination of individual states inside each component. It will become harder to debug the application as  state is unpredictable each time user makes a action . But with Redux the entire state of the application can sit in one single place called store. Whose value is predictable with help of reduces and easy to debug. 

---

### What was the earlier version of Redux ?

(This is a tricky Question, you might be thinking flux is earlier version of redux but both are two different things)

Before redux came into existence by Dan Abramov and Andrew Clark, Community used flux, the way flux works is different than redux. Unlike in redux flux can have any number of store and also unlike in redux state is mutated in the flux and works on event emitters.

---

### What are reducers in Redux ?

Reducers are nothing but pure javascript functions that takes one state and optional payload  and give back new state. 

---

### What are container component and presentational components in React and redux ?
Container Component or smart components are those deal with the data, in case of Redux those are the one that are connected to Store. 

These smart components get the data and pass them as props to Presentational components which does not deal with data but listen to props and render on UI.

---

### Explain the difference between server-side and client-side routing?
https://stackoverflow.com/questions/23975199/when-to-use-client-side-routing-or-server-side-routing

---

### What's the Difference between an Action and an Action Creator in Redux.js?
https://decembersoft.com/posts/whats-the-difference-between-action-and-action-creator-in-redux-js/

---

### What are the benefits of using functional component vs class components?

https://hackernoon.com/react-stateless-functional-components-nine-wins-you-might-have-overlooked-997b0d933dbc

---

### Can a render return multiple div tags?
No, render has to return one div, we can have nested div inside the div but all tags must be wrapped inside a single div

---

### What are the other options to manage state other than redux ?
There are many state management libraries like flux, resub, mobx.

---

### If I ask you to develop a application which framework would you use to do it ?

Subjective answer:
I will use React as I’m more comfortable in react, I will able to better architech the project

---

### How do you style react components ?
React components are styled in the same way a regular html is styled but instead of using class keyword which is reserved keyword in javascript, a __className__(notice the camel case) is used
https://www.menubar.io/5-ways-to-style-react-components

---

### What do you bundle react application ?
Using bundle builders like [webpack](https://codebrahma.com/deploy-react-application-depth-overview-various-options-deploy/) and [parcel](https://medium.freecodecamp.org/how-to-use-parcel-to-bundle-your-react-js-application-d023979e9fe4?gi=31620cf1dfb9)

---

### what is immutable means in store ?

In redux State management,  Reducers are pure functions that means, they take the existing state as argument and return new state. 
As I say new state, they do not change the existing state. In Reducer, we create new state taking the parts of existing state and optional payload from action and create a new state, 
https://stackoverflow.com/questions/34958775/why-should-objects-in-redux-be-immutable

---

### How do you fetch data in react ?

With plain react, componentDidMount is the component life cycle where all the API calls go because this is called after the render and any setState after the render will trigger another setState.

Using redux,
Since API calls are asynchronous, a middleware like redux-thunk or redux-saga is used to make async actions

---

### What are redux middleware ?

---

### What is server side rendering ?

---

### What are different request libraries you are familiar with ?
https://dzone.com/articles/top-javascript-libraries-for-making-ajax-calls

---

### What is webpack-dev-server ?

webpack-dev-server is an additional package alongside of webpack, which is a dev dependency. It is used to automatically compile and build the bundle whenever there are changes to the source folder.

It helps during the development to achieve hot-reload

---

### What are loaders in webpack ?

---

### What are hooks ?
React 16.8.0 is the first release to support Hooks. Hooks are functions that let you “hook into” React state and lifecycle features from function components. Hooks don’t work inside classes — they let you use React without classes.

Below is an example of state hook. Usually we cannot use state inside a functional component but below a hook can create a state inside a functional component.

```javascript

import React, { useState } from 'react';

function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}

```

---

### When do you use functional components vs class based components ?

---

### What are propTypes and defaultProps OR How to validate the props ?

---

### What are synthetic events in react ?

---

### What is a functional component ?

---

### What is React.memo ?

---

### What is webpack ?

---

### How to deploy a react application ?

---

### Which framework do you use to unit-test react component ?

---

### Can you write a sample test case to test if a component is rendering the props ?

---

### What is babel and how do you configure ?
