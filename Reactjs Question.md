### Why React and not any other library ?

Every web framework or library aims to mutate the DOM in most efficient way possible because DOM mutations are expensive.

React is no different, under the hood it uses a mechanism called VDOM which optimizes the DOM mutations way faster than other libraries.

( Interviewee would expect this answer but he can further ask, if directly mutating the DOM is slower how come mutating VDOM and then VDOM intern mutate Real DOM is Faster ? At this point, we understand the interviewee has insight into React Internals so let’s get more verbose about why use React)

A web page is nothing but a HTML template injected with data. But as the applications are growing larger so does the data to show to user. Maintaining the Data manipulation and HTML templates reacting to this data manipulation is going out of control, and HTML shows inconsistent data on the UI.

Angular solves this problem by two way data binding, when a model updates - view is updated and vice versa.
React solves this problem in a declarative way with a unidirectional approach, we only change the model aka state and React ‘reacts’ to this change and finds the optimized way to mutate the view(which uses the VDOM).

The declarative ability of the React helps to focus on the data than on the View, which helps to build large single page applications with out to worry much about the how views would react to these changes.

##### ReactJs

---
### What is VDOM in React ?

VDom or a virtual DOM is exact copy of real HTML dom except it is built as javascript objects with key and values that map to the real DOM nodes, when a change occurs or setState or newProps are detected by a react component, the react notifies the reconciliation algorithm about these change, the algorithm computes the most efficient way to batch this changes to the real dom so the UI updates are faster and are in sync with Data.

---

### What do you mean when you say react is a view library ? or is React follows MVC architecture ?

A traditional MVC architecture has orchestration of Model, View and Controller. While Model holds the Data Model, View is the HTML template and Controller coordinates between view and the model
(Learn more here on how controller plays in between view and model https://stackoverflow.com/a/1015853/3666700)
While React only V(or view) in MVC. Unlike MVC where data flows back and forth, react has unidirectional data flow which means data flow is from the model to the view but not other way round.

##### ReactJs

---

### What is a controlled vs uncontrolled component ? where do you use one over the other ?

A uncontrolled component is any html input component let's say text input, select or may be a checkbox, if the state of the element is maintained by the DOM which I mean on the browser DOM then I would say that as uncontrolled component as we do not have the control over the dom state, but lets say if I would maintain the state of the element inside a react component state and add handler to update the state of the element then I say that as a controlled component.

Simply, 
state maintained by DOM - uncontrolled component 
state maintained by React Component  - controlled component 

Basically we create controlled components to add some validation on the input, like may be avoid typing alphabets into a phone number field or only check the checkbox if certain criteria is met.

##### ReactJs, React Native

---

### Do you have experience with JSX syntax ? or What is JSX ?

JSX stands for Javascript XML. XML stands for eXtensible Markup Language.
JSX is a fancy syntax by facebook react team to write more readable and composable react components. It is a combination of HTML, CSS and Javascript.
Component can also developed using plain vanilla javascript or typescript,. In case of JSX, we would just need extra transpiler configuration like babel to transpile the JSX to equivalent JS so all browsers can compile.

##### ReactJs

---

### What do you understand by Component Life Cycle in React OR Explain Component Life Cycle in React ?

Every component in react undergoes 3 Stages,
--------------------------------

Mounting Stage - Updating Stage - Un-Mounting Stage.

on Mounting Stage we have Constructor if using ES6 Syntax or Get-Initial-State if using ES5 Syntax, Both of the methods are used to set the initial state of the component.

After constructor we have Component-Will-Mount which is removed after the introduction of Get-derived-state-from-props, this was where we used to mutate the state before render kicks off. 

After Component-Will-Mount or Get-derived-state-from-props we have Render function which is the core of the React Library which must be a pure function which returns the View that will be rendered on the DOM.

Follow up: 
What is Pure Function ?
A Pure function is a function which does not have any side effects(side effects: like data fetching.

After Render we have component-did-mount, which is used to make async calls and update the state, when state is updated render function is triggered again with new updated state data and that is how we update the View.

So the sequence of life cycles on Mounting Stage is 

Constructor => Component-Will-Mount => Render => Component-Did-Mount

--------------------------------
After the mounting stage, if we set a new State or the component Receives a new set of properties which are different than the initial set of properties, then the View will undergo a Updating Stage.

When a new set of properties are received by the component then get-derived-states-from-props is triggered but in earlier versions of react we used to have component-will-receive-props, which will trigger with new set of properties, in cases where you want to store the props in the State, then you get a chance to update the state based on new props

Similarly if the state is updated within the component then should-component-update will be triggered and this is the most power ful component life cycle in React Library, this component life cycle decides if the Component should re-render or not, since render is expensive operation we should conditionally return true or false based on new state and new props. A lot of legacy react applications do not have this component life cycle which the UI bit slow.

if the should-component-update returns true then get-snapshot-before-update to capture any information related to previous props or previous state. this is rarely used component life cycle, after which render will be triggered followed up component-did-update

--------------------------------
then finally un-mounting stage, 

We have only one component life cycle method component-will-unmount which we use it to cleaning up things like 1. closing the socket connection if established any previously in component-did-mount or 
2. remove the listeners if added any 
3. clearing the timers etc


--------------------------------
We have one other interesting component lifecycle method which is component-did-catch when a component fails any where between the stages, this is invoked immediately to set the state of the component to error and the on the render we conditionally show a fallback UI and log the error somewhere to investigate why the component failed to render, this type of handling the error and showing the fallback UI is called error boundary in react books.

--------------------------------
Additional Explanations:

if the should-component-update returns true then a component-will-update(which is now removed from react) is called to notify that render is about to start, this is much usual in animations UI where there are transition or fading effects and the component-will-update starts the animation

after component-will-update render is called immediately and then component-did-update is called to notify the render cycle is complete, this is used to stop the animation we started earlier. this is just an example use case though.

This component life cycle is the new addition **React 16.3**, this behaves a as combination of componentWillMount and ComponentWillReceiveProps, means this component life cycle is trigger both on the initial render and subsequent renders

##### ReactJs,Frequently Asked

---

### What is a State in a React ?

A state is nothing but a javascript object to determine the behavior of the component, every time a state change happen in fact a prop change happen, a render function is triggered or UI is re-rendered.

Creating a state

```javascript
constructor(){
  super()
  this.state = {
	//state goes here
   }
 }
```

##### ReactJs,Frequently Asked

---

### Why to use React if there are so many frameworks available in the market ?

React has mechanism called a Virtual DOM which can optimize the mutations on the real DOM, this adds the benefits of faster renders and also react supports Hot-reloading where you can see the changes on the UI as you change through the Code, most of all it is backed by Facebook with huge community support, Also react can help a web developer to be a mobile developer and vice versa as react shares same language JSX. Its called React-Native

React makes writing Views Easier and Its component Based model helps to debug and Isolate the issues from data and views, and it’s extremely efficient because of virtual DOM.
https://blog.syncano.io/reactjs-reasons-why-part-1/

##### ReactJs

---

### How different is componentWillMount Vs component-did-mount ? (M)

componentWillMount is called before the render is called and component-did-mount is called after the render.

##### ReactJs,Frequently Asked

---

## What are hooks in react ?

From React 16.8, react team introduced a new concept hooks which helps to hook features to functional components, before introduction of hooks it wasn’t possible to add a state into a functional components and the only way is to translate the stateless or functional component to class component to introduce state, with introduction of hooks a useState hook can be use to add state in to functional components.

without a state it wasn’t possible make async actions in functional components, so another hook Called useEffect is introduced to make async calls, with combination of useState and useEffect a functional component can be full blown react component with data fetching capabilities.

There are other additional hooks like useContext, useRef, useMemo, useReducer for respective use cases.

##### ReactJs,Frequently Asked

---
## What is UseEffect hook ?

From React 16.8, react team introduced a new concept hooks which helps to hook features to functional components, as part of which UseEffect is introduced to do side effects in functional components.

Basically it works as a combination of component-will-mount, component-will-receive-props and component-will-unmount.

UseEffect will be triggered both on the initial render and on the subs secretive renders.

Second argument in the useEffect uses a array of dependencies which are the properties of the component if any of the properties change useEffect will be triggered again when you do not want this useEffect to be triggered you can pass an empty array as a second argument.

UseEffect can return a function which will be called before the component is unmounted which is equal to component-will-unmount this is useful when you want to remove the socket connection or remove the listeners of the component if you have added previously.

##### ReactJs,Frequently Asked

---

### I would like to add a listener to my react component that will update the state whenever a event is emitted ? How do you add it ?

I would add the listener in component-did-mount and remove the listener in Component-Will-Unmount. We have to make sure to remove the listener in Component-Will-Unmount as you say we are updating the state, updating a state on a un mounted component will show a error message

##### ReactJs

---
### Have you used a context API will you use a context API or redux?

context API is used to avoid the prop drilling in react components what I mean by that is if a property has to be send to a grandchild it has to be drilled through the child but context API will provide a mechanism where you can deliver the props directly to the grand child.

API uses a consumer and a provider and interestingly a consumer will always listen to the nearest provider in the component hierarchy.

Even though context API exist I think I would still use the redux because debugging is a lot easier in redux but I will use the context API in places like themes or user preferences for menu items which should be threaded to every component. But data handling I would have redux.

##### ReactJs

---

### Which life cycle method do you prefer to make a network call and why?(M)

if redux is not in place and I have to make the API calls I will do it in Component did mount because this is the component lifecycle that is called after the render so I can definitely guarantee that set state done in component-did-mount will trigger another render. In earlier versions of React I mean when React got first introduced a lot of React developers used to do network calls in component will mount which resulted in setting a state but since the render is not called as part of the set state but is called as part of the React component lifecycle triggering hierarchy so there is a high chance that a stale state is been rendered

##### ReactJs,Frequently Asked

---

### Which component life cycle is called when Component receive new Props ?

ComponentWillReceiveProps()

Starting from React 16.3, this component is deprecated and replaced with `getDerivedStateFromProps`, unlike `ComponentWillReceiveProps`, `getDerivedStateFromProps` is called on the initial render.

##### ReactJs

---

### How to Optimize renders in React?

It's know that every time a prop or state is changed, a render method is triggered for a component. `ShouldComponentUpdate`
is called just before the render on every state or prop change.

`ShouldComponentUpdate` decides if the component should or should not trigger a render. At any point in the component life time `ShouldComponentUpdate` has access to four pieces of data.

`Previous Props, New Props, Previous State and New State`

`ShouldComponentUpdate` can used to logically compare the above values and decide if a render is needed, if needed `ShouldComponentUpdate`should return `true` or else `false`

##### ReactJs

---

### Do you know any other Libraries like React ?(React is a View Library so there are many. .)

Vuejs, inferno, riotjs

https://github.com/infernojs/inferno
http://riotjs.com/

##### ReactJs

---

### I have Project A , Project B and Project C. I ask you to develop a reusable component to use across all my projects, and I use different styles in three different projects. How will you manage that inside your component ?

I will allow a style prop to pass into the component, internally I will get the style object you passed into( As you know what styles you need to apply based on the project) and apply to my component. I will add in a default style to component and add a additional check is the style object is passed or not into the component, if not a default style will be applied. I can also parse through the style object you passed from defaultProps and validate for any missing css properties and through you a error or warning depending on how important is the style property.

##### ReactJs,Scenario

---

### I have login page on which I have a userId textbox and Password textbox and a SignIn button, next to the Password textbox there is a small Eye icon on which if a user click it will show the password as normal text instead of dot or stars etc. How will you able to do this ?

I will have a state variable called showPassword, which is initially set to false. And on the render function on the Input of the password field on type Property I will throw in a ternary operator if showPassword true then return text if not password. and when user clicks on the eye icon, on every click I will negate the showPassword boolean value and also I will also use the same state variable to switch between open eye icon when password is visible and close eye icon when password is hidden.

##### ReactJs,Scenario

---

### When would you use a Class Component over a Functional Component(Stateless Component)?

If I need a state I would use a class component if not If the component solely depends on props passed into it I would use a functional component or ES6 stateless component.

##### ReactJs,Frequently Asked

---

### When do you use a functional component vs class based component ?

With the introduction of hooks I think I would almost always use the functional components I cannot think of a use case where I would need a class based component where I can use a functional components with Hooks.

Before the introduction of hooks a class based components gets its value in places where I would need a state variable or to do an API fetching or to add socket subscriptions.

##### ReactJs,Frequently Asked

---

### Have you used sockets previously ?

I have used socket connections in a project where I have to track the current location of a GPS device.
Usually we attach the socket on the component did mount and remove the socket connection in component will unmount.

##### ReactJs,Frequently Asked

---

### What are keys in React?

Keys in keys are especially used when mapping over a array to generate views, it would help the Virtual Dom to relocate this Children in the Real DOm and add changes/modification/mutations exactly.

##### ReactJs

---
### When do you use Redux and not use Redux?

If the application do not require a props drilling which means I do not have to pass the props to the grand children and then to the grand children then in that case I would not use the redux as it would be a overkill to use redux in such a small application but in applications where there is a complex state and a lot of state manipulation goes I would use the redux

##### ReactJs

---

### Can we not Mutate the state directly by saying this.state.variable = value ?

A state can only happen through setState because it chains other set states previously called so that the state is mutated once at a time.
To know is the setState happen, we can pass in a second argument inside the setState kinda callback which is called only after the setState is called.

##### ReactJs

---
##### Is setState synchronous or asynchronous ?

A set state in React is in asynchronous call because under the hood React uses reconciliation algorithm to  compute the best way to update the DOM which is asynchronous and this is the reason we have a second argument in the set state which is a callback function to read the state which is set, There are very high chances that trying to read a state variable immediately after the set state will give us a stale or old state if not accessed within a callback function
##### ReactJs

---

### What are the some of the disadvantage of React ?

React is just a view library unlike other UI frameworks , and its JSX syntax which is harder to understand for beginners but will be fun when you get the understanding.

##### ReactJs

---

### How much hands-on experience with backend coding do you have? did you work on any services for your current project if so, what services?

I have two years of experience working with backend code. I am familiar with springBoot on Java and Nodejs for building API’s. In my current project I have not created services from the scratch but tweaked few services to match the acceptance criteria for the new features we were building.

##### Backend

---

### What is the difference between React vs react native?

React is used for building the web apps. While React native is used for building mobile apps.

##### ReactJs,React Native

---

### Difference between React and Angular ? (M)

https://www.codementor.io/chrisharrington/react-vs-angularjs-how-the-two-compare-8t6f1ioan
On a Higher level, React is only View where has Angular is MVC

##### ReactJs

---

### Can be Props be mutated in React? If not Why ??

Props are immutable
Props are the data that are passed into the component from the parent component, the only source of truth should be parent.
If it is required to mutate the props, pass a function to mutate the data in the parent component to the child as prop and let the mutation happen in the parent.

https://stackoverflow.com/questions/27643504/react-js-warning-dont-set-the-props-property-of-the-component-mutate-the-exis

##### ReactJs,Frequently Asked

---

### How to pass the data from child back to parent ?

Data is passed from child to parent through callback functions.
Similar to passing the props from the parent to child, a function is passed as prop to the child and child triggers the function with arguments which are passed to the parent

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

##### ReactJs,Frequently Asked

---

### Can we pass a react component as prop to child react component?

React component can be passed by wrapping inside a parent component and within the child component that can access as this.props.children
https://mxstbr.blog/2017/02/react-children-deepdive/

##### ReactJs

---

### What are refs in React ?

Every Component in React can be given a ref on the view inside the render/ This is how we can directly access the DOM element of the React Component.
The interesting part here is it carries all the user defined functions inside the React Component

##### ReactJs,Frequently Asked

---

### What are Higher order Components in React ?

https://medium.com/@franleplant/react-higher-order-components-in-depth-cf9032ee6c3e

Other places to look
https://tylermcginnis.com/react-interview-questions/
https://www.toptal.com/react/interview-questions
https://www.codementor.io/blog/5-essential-reactjs-interview-questions-du1084ym1

##### ReactJs

---

### Talk about some components in react native you are using specifically any APIs?

I have used FlatList, SectionalList, VirtualizedList, SafeAreaView for notch devices. I have worked on device APIs on
`Android: BackHandler, PermissionsAndroid, ToastAndroid etc`
`iOS: ActionSheetIOS etc`
`Common: ActivityIndicator, Dimensions, PixelRatio,RefreshControl etc`

##### React Native

---

### Can we do a React Application without Redux ?

Absolutely Yes, Redux just a state management library. We can use a high order component to manage the state.
https://medium.com/@dan_abramov/you-might-not-need-redux-be46360cf367

##### ReactJs,Frequently Asked

---

### Can you explain Redux on a high level ? or Can you explain redux flow ?

When an Action is dispatched by may be a user action like a click on a button or typing on an input field or may be network call action or it may be by business logic. 

The Action dispatched has two parts in it, one is mandatory TYPE and another is optional PAYLOAD. 

When store listens to this ACTION, it will pass down the ACTION to the all the reducers, each reducer will take this ACTION and look for TYPE and then re-create a NEW STATE based on previous STATE and return this NEW STATE.

STORE is updated with NEW STATE received, and with in the component REDUX is connected to react components using CONNECT method from `react-redux` package.

The CONNECT Method is a curry function which will take two arguments, of which second is optional. First is MAP-STATE-TO-PROPS function which will take the REDUX STORE and pass it to the components as PROPS, and the second argument is MAP-DISPATCH-TO-PROPS which will pass the ACTIONS so that the components can trigger the ACTION which continues the cycle.

In a nut shell, the flow is VIEW to ACTION, ACTION to STORE, STORE to VIEW.

##### ReactJs,Frequently Asked

---

### What are the methods that connect the redux store and actions to the component ?

MapDispatchToProps and MapPropsToStates

##### ReactJs

---

### How Does Redux help in State management ?

If you have a application whose components are nested heavily, it requires a lot of callback functions and props to be passed from parent to child so on and so forth. At a point it would be hard to determine the state of the application as it is combination of individual states inside each component. It will become harder to debug the application as state is unpredictable each time user makes a action . But with Redux the entire state of the application can sit in one single place called store. Whose value is predictable with help of reduces and easy to debug.

##### ReactJs,Frequently Asked

---

### What was the earlier version of Redux ?

(This is a tricky Question, you might be thinking flux is earlier version of redux but both are two different things)

Before redux came into existence by Dan Abramov and Andrew Clark, Community used flux, the way flux works is different than redux. Unlike in redux flux can have any number of store and also unlike in redux state is mutated in the flux and works on event emitters.

##### ReactJs

---

### What are reducers in Redux ?

Reducers are nothing but pure javascript functions that takes one state and optional payload and give back new state.

##### ReactJs

---

### What is Context API ?

The context API is basically a React’s own home grown way to replace complex state management libaries like flux and redux. The core idea of context api to avoid props drilling across the components and provide a global state. Usually context API can be used for values that reflect across the app like themes, authentication or preferred language.

There are 3 different pieces to hook up context to a React App. The context itself which has a default value and the callback to change the value, the provider which passes the values down the component tree and the consumer that consumes the passed in values. The cool thing about the consumer is that it only listens to the nearest provider higher in the component tree, this allows to nest multiple providers.

##### ReactJs

---

### What is Prettier ?

Prettier is a code formatter that helps to format the code based on the .prettierrc(say it as dot prettier rc file) config file. it’s basically help to auto format the code looking for common code guidelines like missing semicolons or indentations or usage of particular code styles based on config file. Usually developers in an organization come together and decide on certain code guide lines which can be integrated into the workspace so new developers can easily able to contribute aligning towards already setup guide lines. prettier can also integrated with a build pipeline to auto format the pull requests which can save developers on code reviews.

##### Tools

---

### What are container component and presentational components in React and redux ?

Container Component or smart components are those deal with the data, in case of Redux those are the one that are connected to Store.

These smart components get the data and pass them as props to Presentational components which does not deal with data but listen to props and render on UI.

##### ReactJs,Frequently Asked

---

### Explain the difference between server-side and client-side routing?

https://stackoverflow.com/questions/23975199/when-to-use-client-side-routing-or-server-side-routing

##### ReactJs

---

### What's the Difference between an Action and an Action Creator in Redux.js?

https://decembersoft.com/posts/whats-the-difference-between-action-and-action-creator-in-redux-js/

##### Redux

---

### What are the benefits of using functional component vs class components?

https://hackernoon.com/react-stateless-functional-components-nine-wins-you-might-have-overlooked-997b0d933dbc

##### ReactJs,Frequently Asked

---

### Can a render return multiple div tags?

No, render has to return one div, we can have nested div inside the div but all tags must be wrapped inside a single div

##### ReactJs

---

### What are the other options to manage state other than redux ?

There are many state management libraries like flux, resub, mobx.

##### ReactJs

---

### If I ask you to develop a application which framework would you use to do it ?

Subjective answer:
I will use React as I’m more comfortable in react, I will able to better architect the project

##### ReactJs

---

### How do you style react components ?

React components are styled in the same way a regular html is styled but instead of using class keyword which is reserved keyword in javascript, a **className**(notice the camel case) is used
https://www.menubar.io/5-ways-to-style-react-components

##### ReactJs

---

### What do you bundle react application ?

Using bundle builders like [webpack](https://codebrahma.com/deploy-react-application-depth-overview-various-options-deploy/) and [parcel](https://medium.freecodecamp.org/how-to-use-parcel-to-bundle-your-react-js-application-d023979e9fe4?gi=31620cf1dfb9)

##### ReactJs

---

### What is immutable means in store ?

In redux State management, Reducers are pure functions that means, they take the existing state as argument and return new state.
As I say new state, they do not change the existing state. In Reducer, we create new state taking the parts of existing state and optional payload from action and create a new state,
https://stackoverflow.com/questions/34958775/why-should-objects-in-redux-be-immutable

##### Redux

---

### How do you fetch data in react ?

With plain react, component-did-mount is the component life cycle where all the API calls go because this is called after the render and any setState after the render will trigger another setState.

Using redux,
Since API calls are asynchronous, a middleware like redux-thunk or redux-saga is used to make async actions

##### ReactJs,Frequently Asked

---

### What are redux middleware ?

Middleware are the utility libraries that act in between actions and redux store. Middleware are useful in a lot of use cases like for doing async actions, a thunk of saga middleware is used. To log actions and how store is responding to those actions, a redux logger middleware is used.

Middleware are configure on creation of the store

```javascript

import { createStore, combineReducers, applyMiddleware } from 'redux'

const sampleApp = combineReducers(reducers)
const store = createStore(
  rootReducer
  applyMiddleware(logger, thunk) // <== Logger, thunk are the middlewares
)

```

[Learn More](https://redux.js.org/advanced/middleware)

##### Redux

---
### Have you used redux saga ?

Yes I have used read Sags in my previous application as well as in current application are redux-saga is a middleware which is as part of the Redux, it's a middleware which helps us to do a asynchronous actions like data fetching. 

Under the hood redux Saga uses generator functions which have capabilities to pause the function execution and restart as needed, Each time a generator function is called it pauses at the first encountered yield at which we make async calls and when async call is completed we PUT the action which dispatches a ACTION object which is listened by the reducers to take appropriate state creation.

Interesting part about Sagas is that they have abilities to drop repetitive actions if fired continuously using take-latest utility which works very similarly to debounce function in javascript.
##### Redux

---
### What is a higher order component in React can you give me an example ?
A higher order component is more like a design pattern than a feature from the Facebook I meant React. 

In a nutshell a higher order component basically takes a base component and then returns a updated component Otherwise a H-O-C is a pattern to share logic across the components.

For Example:
Let's say I have two list components which basically gets the data from the two different APIs and but so same type of filtering on the list items, in that case I can create a HOC and move the filtering logic into HOC and have different View components for each List, infact I can also move the fetching the date into HOC with added API prop for the HOC.
##### Redux

### What is server side rendering ?

[Learn More](https://medium.freecodecamp.org/demystifying-reacts-server-side-render-de335d408fe4)

##### ReactJs

---

### What are different request libraries you are familiar with ?

https://dzone.com/articles/top-javascript-libraries-for-making-ajax-calls

##### Javascript

---

### What is webpack-dev-server ?

`webpack-dev-server` is an additional package alongside of webpack, which is a dev dependency. It is used to automatically compile and build the bundle whenever there are changes to the source folder.

It helps during the development to achieve `hot-reload`

##### ReactJs

---

### What are loaders in webpack ?

##### Webpack

---

### What are hooks ?

`React 16.8.0` is the first release to support Hooks. Hooks are functions that let you “hook into” React state and lifecycle features from function components. Hooks don’t work inside classes — they let you use React without classes.

Below is an example of state hook. Usually we cannot use state inside a functional component but below a hook can create a state inside a functional component.

```javascript
import React, { useState } from "react";

function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```

##### ReactJs

---

### Do you have experience with Hooks concepts? Explain what it is?

I am a huge fan of hooks. It really helps to cut down a lot of boilerplate code and eliminates the confusion of “this” for the new react developers. It also helps to cut down all the component life cycles. It still gives the same power as the class component to a functional component. Hooks are introduced in React 16.8. Before introduction of hooks, it was not possible to add state inside a functional component.
Examples of Hooks: useState, useRef, useContext,useEffect, useMemo etc.

##### ReactJs,React Native

---

### Difference between useRef hook? And useContext ?

useRef is used to attach a reference to the DOM element from the React world. refs basically give a direct access to the DOM element which helps to mutate the DOM directly skipping the Virtual DOM cycle.
Whereas useContext is used to pass the props from a parent to a grand child by skipping the components in between. It eliminates prop drilling and gives access to the props to all the nested components. This is achievable through a consumer and provider. One interesting criteria of useContext is it always matches to the closest provider up in the component hierarchy.

---

### What is your authentication experience on backend and frontend?

I have integrated authentication using JWT and singleSignOn.

---

### What are propTypes and defaultProps OR How to validate the props ?

---

### I want to make a few API calls from react native, how can I achieve that?

There are multiple ways to do this.
`Approach 1:` If we are using a class-based component, we can make the api calls in the component-did-mount and update the state to trigger another render cycle with fetched data.
`Approach 2:` If we are using a functional component, we can make an api calls by using useEffect() hook and update the state to trigger another render cycle with fetched data.
`Approach 3:` If we are using the state management library like Redux, we can try fetching the data using middlewares like Redux Thunk or Redux Saga to trigger asynchronous action and update the store, which will update all the connected components.

---

### What are synthetic events in react ?

---

### What is a functional component ?

A functional component or ES6 stateless components are those which does not have state and component life cycles like in class component.

It depends on the props and callback functions from the parent

_functional components are also called a presentation components or dumb components_

---

### What is React.memo ?

A functional component always renders when a parent renders even when props does not change. The unnecessary renders can be avoided and add ability to only render when props change can be achieved using react.memo

_React.memo is equivalent of class pure component_

---

### What is webpack ?

Webpack is bundler which take all the source code and [bundles into equivalent minified version](https://medium.freecodecamp.org/how-to-build-modern-applications-with-webpack-c81ccf6dd54f). There are lot of features of webpack like code-splitting, uglification

---

### How to deploy a react application ?

Like any other web application, react-apps are bundled using bundlers like grunt,gulp or webpack. The bundles are copied to a server from which there are served.

Example:

1. Build the bundle using npm run build, this will build the source files and create a folder called build which has all the minified source files and index.html which is pointing to the this bundles.

- build
  - static _// has all the minified files_
  - index.html _// has base html and script pointing to static files_
  - assets _// all the images, gif, videos or any_
- source
  - components // react components
- node_modules
- package.json
- index.js
- index.html

---

### Which framework do you use to unit-test react component ?

Enzyme and Jest

---

### Can you write a sample test case ?

Let's say you want to test if a component is rendering a 2 input fields on a login page

```javascript

describe('<MyComponent />', () => {
  it('renders input field', () => {
    const wrapper = shallow(<MyComponent />);
    expect(wrapper.find(<input />)).to.have.lengthOf(2);
  });
}

```

---

### What is babel and how do you configure ?

As browsers do not support JSX natively, a transpiler is used to convert JSX to javascript. The Transpiler is the Babel, it is configured using .babelrc file inside the root level of the application.

---

### Tell me about a technology you recently learned ? why did you choose to learn it and were you able to leverage it on a project.

I recently learned React-testing-library to unit test react components, I very much liked this library for the way it does the unit testing.. All the previous testing libraries I have used to test the react component were testing the implementation details like where is the div or span in the node tree and parsing the tree for the content and asset on the test. This methodology of testing breaks the unit tests if the HTML node structure changes or if the components are further breken down.. But the new testing library assets on the text and visibility of the elements rather than where they are placed in the node tree..  Testing the component in a way the user interacts with it.. The user does not have a clue on the implementation details and this is how unit testing should be done as well.. The react-testing-library tests the functionality over the implementation details and provides very clean APIs like fireEvent and render which mimics user interactions on the browser.. I pitched this to my team when we were looking for adding testing library to our project and we successfully was able integrate the unit testing library and we were able to achieve 95% of code coverage. I am really happy with the decision as it gave lot of more confidence to the developers to make changes without breaking the existing functionality, we further integrated with the CI/CD tool to run the test cases on the pipeline to  run over pull requests to save code review time to the developers.

---

### Why do you prefer React-Native over native development ?

---

### What are the advantages of using react-native over other hybrid technologies ?

---

### Did you work on the new component life cycles of reactjs ?

---

### Do you think react native is a good option to develop games ?

---

### What is the weirdest thing you discovered while learning react ?

---

### Is react faster or Angular faster ?

---

### How do you install/link dependencies in react-native application ?

---

### What do you look for when you implement FlatList ?

---

### Do you think animations on React-native are better or on Native is better ?

---

### Are you familiar with interaction manager ? will you use this to make animations better ?

---

### Are you familiar with animated API ?

---

### What is the difference between flex box on web vs flex box on mobile ?

---

### Which component life cycle will you use if you have to make API calls and why do you choose that?

---

### Can I make API calls in componentWillMount instead of component-did-mount ?

---

### Why should I use functional components instead of class based components ?

---

### Let say I have component that renders 5 times because of props change, how many times does the useEffect will be called ?

---

### What happens if I do not specify any arguments to the useEffect how many times it is called ?

---

### what happens if I pass empty array as an argument ?

---

### If I have to do some house keeping on the component, where should I do on useEffect?

---

### How can we differentiate between prod and development environments ?

---

### I have navigation screens say A, B, C, D screens. On iOS user should see only to A and C screens, while on Android user should only B and D screens.

### This is a two part question:

### 1. How to you handle the navigation based on the platform ?

### 2. When generating the APK how can get rid of the A and D code and similarly while building iOS how can avoid including B and D code, I do not like to have any residue because it will increase app size ?

---

### Do you deploy APK and IPA files to the testing environment like test-flight, hockey using Pipeline ?

---
### What is localStorage and sessionStorage ? when do you use one over the other ?

Both local storage and session storage are few megabytes of storage on browser.

I would use local storage for non-sensitve data like user preferences like dark mode or light mode etc or may be understand if the user is visited very first on to the site to show some first time promotions etc.

Local storage is retained as long as browser cache is retained

while I will use session storage for sensitive information like user authentication token or data related to personal identified information etc. the session storage will be cleared as soon as a browser tab is closed.

Local storage can be shared across multiple tabs of the browser while session storage cannot be shared which makes it more secured.

---

### As we need with authentication, we need secure the tokens somewhere in the App, how do you make sure these token are secure ?

The easiest way to store data in a app is to use the Async storage which stores data in a key value pair. But the problem with Async storage is that its not encrypted thought is it persistent.

To overcome this issue, we can make use of platform specific options like keychain on iOS or keystore on Android. Since respective platforms have their own extra layer of protection around keychain and keystore the security part will be managed by the operating system itself, so we can confidently store the sensitive information here. Added, there are variety of libraries that abstract away the process of setting and getting values from these secured location, one I am familiar with react-native-keychain library.

One thing to be noted though is that the older versions of Android do not have this concept of keystore and it is only available from API Level 23.

Follow up question:
then in that case, where can we store the token security for android versions before API Level 23.

before Android introduced keystore, we used to store them in shared preference which is quite exposed to all the third party apps, to prevent this Android introduced keystore.

Read More: https://resources.infosecinstitute.com/topic/android-hacking-security-part-9-insecure-local-storage-shared-preferences/

---

### When you make a API call on the App, how do you make sure that you are not blocking the UI thread ?

---

### What is the most difficult component you build that you thought was easy initially both on react and React- native ?

I can definitely say building a carousal component on the react was the toughest component that I built. I was easily able to build a component using a transform CSS property with all the functionality needed basically the way it works is to arrest the scroll of the view and only move the scroll programmatically using the Next and Previous buttons but the challenge surfaced when accessibility team reached out saying carousal component is scrollable when used with keyboard Tab Navigation and Next button never get disabled on the last slide and clicking on Next completely breaks the UI.

I immediately know why it breaks the UI after the clicking the Next button on the last slide as it attempts to scroll beyond the viewport of the component which breaks the Math logic i did but I was not sure why the scroll is not arrested, I did my investigation and found accessibility engine scrolls to the next element in the DOM hierarchy and brings the HTML element in to the View Port if hidden which in my case the next slide was hidden so it scroll to bring it into the view port ditching the Scroll lock I did.

So I had to go back and re implement the component and instead of hiding the next slides, I used visibility: none and logically render the slide and avoid the scroll view all to gather and and added CSS key frames for the scrolling effect animation. 

---

### What are the different authentication methods like oAuth you are familiar with ?

I have worked with ADAL(Active Directory Authentication Library - owned by microsoft) previously for multi factor authentications, but recently as microsoft has moved towards to MSAL(Microsoft Authentication Library) to provide access to personal accounts while retaining the same level os security.

I also worked with OAuth authorization protocol that can use JWT as a token, which is added to the header on every request.

---

### How do you set and getProps, what methodology you use ?

---

### What are the few different ways where you can show invalid input inside a text field?

---

### How do you errors and handle exceptions app crashes in your app ?￼￼￼

---

### Can you please walk me through the process of debugging an app when it is crashing in the prod.

---

### What are the top three things you would consider if you are starting an app from the scratch? ￼

---

### Can you please walk me through a process of where you have two different code bases for android and iOS and you want to create a single repository of React Native how would you start approaching while communicating to both the teams and do not stopping their contributions to their respective repositories ?

---

### I have a standard native android and iOS app and I would like to introduce React Native into few screens ￼how can I get started￼?

---

### Can you elaborate a little bit on how would you approach a state management library ?

---

### What methodologies do you use to communicate about the new available components in your library that can be used to build the features across other apps ?

---

### If there is a new requirement which was not told previously that you want to convert React Native app into a browser app how would you do this ??

---

### What do you prefer a objective C, Swift, kotlin, React Native or flutter. ?

---

### Can you talk a little bit about the bundling process on reactjs and as well as React Native￼ ??

---

### What mechanisms do you use to log app crashes to store them to remote server￼ ?

---

### Can you walk me through the process where you would like to validate text input against by a remote API for example if a user ID already taken or not.

---

### Did you bring in any design ideas for a better user experience tell me about a scenario where you brought in a value addition to the design ? ￼

---

### Tell me about your recent work ?

---

### What are the advantages of graphQL ?

---

### How did you achieve responsiveness on Reactjs?

---

### What is the complex bug you fixed on your project ?

---

### Can you please write a simple graphQl query using hooks ?

---

### What is the equivalent of component-did-mount in functional Components ?

---

### What are the top 3 things you will check when you see application is slow ?

---

### Have you used Mobx ?

---

### Difference between class components and pure class components ?

---

### What is strict mode in javascript ? not double equal or triple equal ?

---

### What are the benefits of typescript ?

---

### Are you comfortable using Javascript on client side or server side ?

---

### What is API gateWay ?

---

### Have you worked on RAML ?

---

### Difference between firebase and mongoDb ? when will you these any of these ?

---

### Do you have any experience working with Charts ?

I have integrated D3 charting library(Bar,Pie, Line) to build a admin dashboard to provide a very high level overview of the various system analytics and health checks, I am also familiar with integrative live charting using websockets to update the charts in real time. I have developed dashboards using vanilla version of D3 library and also with react-charts-d3 which uses D3 library under the hood. I am also familiar with highcharts which is a corporate version and alternative to D3.

---
### Why have react imported on top of every component file even though when not used in creating a functional component ?

##### ReactJs,React Native

---

### What is the differences between react version 14,version 15,version 16 and version 17 ?

##### ReactJs

---

### Why hooks cannot be in conditions ?

##### ReactJs

