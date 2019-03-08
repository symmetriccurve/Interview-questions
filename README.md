# Interview-questions

MOST ASKED QUESTION IN EVERY INTERVIEW  are marked as M next to question.

React
What do you understand by Component Life Cycle in React ? (M)
Why to use React if there are so many frameworks available in the market ?

Javascript


CSS

General UI

WorkRelated

What do you understand by Component Life Cycle in React ? (M)
Explain Component Life Cycle in React ? (M)

Almost all the interview questions are based on component life cycles

Every component in react undergoes three phases, 
Initialization phase, updating phase, unmounting phase.

On INITIALIZATION PHASE we have: 

Constructor if you are using ES6 Syntax or getInitialState if using ES5 Syntax 
	This sets the initial state of the component

ComponentWillMount 
	We use this to update the state even before UI Elements shows up on DOM

Render
	The return of this function is what is seen on the UI, it returns Views wrapped inside a single div( Follow up Question: What do you mean by single div, can we not return multiple divs, go to (1A) )

On the UPDATING PHASE we have:

ComponentWillReceiveProps
	Everytime a component receives new set of props, this component life cycle is triggered with a argument which are new set of props

ShouldComponentUpdate
	This component life cycle when used appropriately will avoid any unnecessary renders of the component(Follow up Question: What do you mean by unnecessary renders), depending on the business logic it might return true or false, if it returns true a render will be triggered, if not render is avoided.

ComponentWillUpdate
	If ShouldComponentUpdate returns true componentWillUpdate is triggered

Render
ComponentDidUpdate
	ComponentDidUpdate is called after the Render

On the UNMOUNTING PHASE we have:

ComponentWillMount
	Is called when component is about to be unmounted from DOM


What is a State in a React ? (M)

A state is nothing but a javascript object to determine the behaviour of the component, every time a state change happen in fact a prop change happen, a render is triggered or UI is re-rendered.


Why to use React if there are so many frameworks available in the market ?

React has mechanism called a Virtual DOM which can optimize the mutations on the real DOM, this adds the benefits of faster renders and also react supports  Hot-reloading where you can see the changes on the UI as you change through the Code, most of all it is backed by Facebook with huge community support, Also react can help a web developer to be a mobile developer and vice versa as react shares same language JSX. Its called React-Native

React makes writing Views Easier and Its component Based model helps to debug and Isolate the issues from data and views, and it’s extremely efficient because of virtual DOM.
https://blog.syncano.io/reactjs-reasons-why-part-1/


How different is componentWillMount Vs ComponentDidMount ? (M)

componentWillMount is called before the render is called and ComponentDidMount is called after the render.


What are the life cycle methods that are called on first render ?

Constructor 
ComponentWillMount
Render
ComponentDidMount


I would like to add a listener to my react component that will update the state whenever a event is emitted ? How do you add it ?

I would add the listener in componentDidMount and remove the listener in ComponentWillUnmount. We have to make sure to remove the listener in  ComponentWillUnmount as you say we are updating the state, updating a state on a un mounted component will show a error message 


Which life cycle method do you prefer to make a network call ?(M)

ComponentDidMount()
https://stackoverflow.com/questions/41612200/in-react-js-should-i-make-my-initial-network-request-in-componentwillmount-or-co


Which component life cycle is called when Component receive new Props ?

ComponentWillReceiveProps()


How to Optimize renders in React ?(M)

It;s know that every time a prop is changed or state is changed inside the component a render method is triggered. ShouldComponentUpdate is LifeCycle method that can be logically used to manage the render cycles, this method can return a true or false logically to avoid a re-render.


Do you know any other Libraries like React ?(React is a View Library so there are many. .)

https://github.com/infernojs/inferno
http://riotjs.com/


I have Project A , Project B and Project C. I ask you to develop a reusable component to use across all my projects, and I use different styles in three different projects. How will you manage that inside your component ?

I will allow a style prop to pass into the component, internally I will get the style object you passed into( As you know what styles you need to apply based on the project) and apply to my component. I will add in a default style to component and add a additional check is the style object is passed or not into the component, if not a default style will be applied. I can also parse through the style object you passed from defaultProps and validate for any missing css properties and through you a error or warning depending on how important is the style property.


I have login page on which I have a userId textbox and Password textbox and a SignIn button, next to the Password textbox there is a small Eye icon on which if a user click it will show the password as normal text instead of dot or stars etc. How will you able to do this ?

I will have a state variable called showPassword, which is initially set to false. And on the render function on the Input of the password field on type Property I will throw in a ternary operator if showPassword true then return text if not password. and when user clicks on the eye icon, on every click I will negate the showPassword boolean value and also I will also use the same state variable to switch between open eye icon when password is visible and close eye icon when password is hidden.


When would you use a Class Component over a Functional Component(Stateless Component)?(M)

If I need a state I would use a class component if not If the component solely depends on props passed into it I would use a functional component or ES6 stateless component.


What are keys in React?

Keys in keys are especially used when mapping over a array to generate views, it would help the Virtual Dom to relocate this Children in the Real DOm and add changes/modification/mutations exactly. 


Can we not Mutate the state directly by saying this.state.variable = value ?

A state can only happen through setState because it chains other set states previously called so that the state is mutated once at a time.
To know is the setState happen, we can pass in a second argument inside the setState kinda callback which is called only after the setState is called.


What are the some of the disadvantage of React ?

React is just a view library unlike other UI frameworks , and its JSx syntax which is harder to understand for beginners but will be fun when you get the understanding. 


Difference between React and Angular ? (M)

https://www.codementor.io/chrisharrington/react-vs-angularjs-how-the-two-compare-8t6f1ioan
On a Higher level, React is only View where has Angular is MVC


Can be Props be mutated in React? If not Why ??

Props are immutable 
Props are the data that are passed into the component from the parent component, the only source of truth should be parent.
If it is required to mutate the props, pass a function to mutate the data in the parent component to the child as prop and let the mutation happen in the parent.

https://stackoverflow.com/questions/27643504/react-js-warning-dont-set-the-props-property-of-the-component-mutate-the-exis


Can we pass a react component as props to child react component?

React component can be passed by wrapping inside a parent component and within the child component that can access as this.props.children
https://mxstbr.blog/2017/02/react-children-deepdive/


What are refs in React ?(M)

Every Component  in React can be given a ref on the view inside the render/ This is how we can  directly access the DOM element of the React Component. 

The interesting part here is it carries all the user defined functions inside the React Component 


What are Higher order Components in React ?(M)

https://medium.com/@franleplant/react-higher-order-components-in-depth-cf9032ee6c3e

Other places to look 
https://tylermcginnis.com/react-interview-questions/
https://www.toptal.com/react/interview-questions
https://www.codementor.io/blog/5-essential-reactjs-interview-questions-du1084ym1


Can we do a React Application without Redux ?

Absolutely Yes, Redux just a  state management library. We can use a high order component to manage the state.
https://medium.com/@dan_abramov/you-might-not-need-redux-be46360cf367


Can you explain Redux on a Higher Level ?

When an Action is trigger by user interaction of network call or if by business logic, the Action carries optional payload and a action type which intern listened by all the reducers and a reducer having a corresponding action type creates a new state and returns.

This updates the store with new state, and within the component. Redux is connected to Redux using Connect method from React-redux. There are two method associated or that are triggered when a store change happen. MapDispatchToProps and MapPropsToStates .MapPropsToStates pushes the new props and vire is updated accordingly . 

What are the methods that connect the redux store and actions to the component ?
MapDispatchToProps and MapPropsToStates


How Does Redux help in State management ? 

 If you have a application whose components are nested heavily, it requires a lot of callback  functions and props to be passed from parent to child so on and so forth. At a point it would be hard to determine the state of the application as it is combination of individual states inside each component. It will become harder to debug the application as  state is unpredictable each time user makes a action . But with Redux the entire state of the application can sit in one single place called store. Whose value is predictable with help of reduces and easy to debug. 


What was the earlier version of Redux ?

(This is a tricky Question, you might be thinking flux is earlier version of redux but both are two different things)

Before redux came into existence by Dan Abramov and Andrew Clark, Community used flux, the way flux works is different than redux. Unlike in redux flux can have any number of store and also unlike in redux state is mutated in the flux and works on event emitters.


What are reducers in Redux ?

Reducers are nothing but pure javascript functions that takes one state and optional payload  and give back new state. 

What are container component and presentational components in React and redux ?
Container Component or smart components are those deal with the data, in case of Redux those are the one that are connected to Store. 

These smart components get the data and pass them as props to Presentational components which does not deal with data but listen to props and render on UI.


Explain the difference between server-side and client-side routing?

https://stackoverflow.com/questions/23975199/when-to-use-client-side-routing-or-server-side-routing


What's the Difference between an Action and an Action Creator in Redux.js?

https://decembersoft.com/posts/whats-the-difference-between-action-and-action-creator-in-redux-js/


What are the benefits of using functional component vs class components?

https://hackernoon.com/react-stateless-functional-components-nine-wins-you-might-have-overlooked-997b0d933dbc


Can a render return multiple div tags? (1A)

No, render has to return one div, we can have nested div inside the div but all tags must be wrapped inside a single div


What are the other options to manage state other than redux ?

There are many state management libraries like flux, resub, mobx.


If I ask you to develop a application which framework would you use to do it ?

Subjective answer:
I will use React as I’m more comfortable in react, I will able to better architech the project


How do you style react components ?

https://www.menubar.io/5-ways-to-style-react-components


What do you bundle react code ?

Using bundle builders like webpack and parcel


what is  immutable means in store ?

In redux State management,  Reducers are pure functions that means, they take the existing state as argument and return new state. 
As I say new state, they do not change the existing state. In Reducer, we create new state taking the parts of existing state and optional payload from action and create a new state, 
https://stackoverflow.com/questions/34958775/why-should-objects-in-redux-be-immutable


How do you fetch data in react ?
What are redux middleware ?
What is server side rendering ?
What are different request libraries you are familiar with ?
https://dzone.com/articles/top-javascript-libraries-for-making-ajax-calls
What is webpack-dev-server ?
What are loaders in webpack ?
What is babel  and how do you configure ?


General UI Questions:

What is cross site scripting ? and how to avoid it ?

how to achieve cross browser issues mainly on ie ?
What are the some of the issues using flexbox in Ie ?
Which version of IE are you currently working on ?
We used browserStack to test the cross browser functionality and also had a touch screen windows laptop and few tablets to test the application,
Most of the issues were caught on the windows machines especially on IE, one such was event emitter. By default windows 8 IE does not provide a window object of event emitter,

I used eventemitter polyfill to add this feature to IE.


What are new features of HTML5 ?

datalist,contentEditable
Few new tags are being added in to HTML5. Some of them are
<input type=’datetime’>
On top of input attributes which we already have like type= password, type= text etx, now we also able to input date, time or both date and time using the attribute:
Datetime

<canvas>
To have custom graphics on top of SVGs

<section> and <article>
The <article> and <section> tags are two more semantic tags that will boost your search engine visibility. Articles can be composed of multiple sections, and a section can have multiple articles. An article represents a full block of content, and a section is a piece of a bigger whole.


What is a DOCType in Html Document ?

Doctype let the browser know which version of HTML to use.


Generic Questions: 

What are different http status codes ?


What is the response status/code if successful on GET ?

200- ok


What is the response status/code if successful on PUT ?

201 - created


Challenges you faced in your project ?

There were multiple challenges in the project initially due to the lack of code structure and unable to think the complex use cases in the future, one such thing is a Scheduler component designed by one of the senior developers in JQuery, 

The component is basically a UI pane, that user can able to drag and drop icons to create a timeline, initially the icons were only able to be dragged in intervals of 5 minutes to create a timeline in phase 2, as we progressed into phase three the backend was able to process in intervals of one minute. 

Since the timeline was divided in to 288 parts(24 hours * 60 minutes = 1440 minutes , Each block is 5 minutes so 1440/5 = 288 blocks  )

Moving in terms of 5 minutes was easy using mouse, but moving exactly 1 minute left and right was hard and needs precise mouse movements.

I tried to convince the upper management to expand the timeline and make it scrollable, since it is being around 1 year and end users will not be able understand the horizontal scroll and  to retain the user experience, they disapproved the idea of expanding. Later, I came up with an idea to use the keyboard left and right arrow keys to fine tune the icons having the the position or time on the icon as tooltip. 

The other challenge was lack of state management for such a huge application. The state of the application was managed using high level parent components that pass the date to child, this was tedious as there are lot of callbacks and data passing to and fro. 

It was very hard to reproduce issues, and took a lot of time debugging following up each callback and testing the data to each component. 


I introduced redux and was slowly migrated components in terms of functionalities. 


how do you communicate with  back end team ?

We have daily standup’s about the progress of the sprint.Apart from stand up we update the tickets on jira with comments and ise slack internally. If something is ambiguous or not clear we personally set up meetings with one on one. But doing the sprint planning meeting at the start of every alternate week, I would like to get the most of the information and plan the sprint accordingly


Why Angular 3 is skipped ?

https://stackoverflow.com/questions/41164866/why-was-angular-3-skipped-and-what-are-the-major-differences-in-angular-4-beta

Due to this misalignment of the router package’s version, the team decided to go straight for Angular v4.


Angular 5 vs Angular 4 Angular or 2 Angular.js ?

There is no major breaking changes in Angular 4 and Angular 5,
Angular 1 OR Angular.js 
Angular 2 is complete rewrite of Angular 1 or Angular.js


What is charset in the HTML file ?

Basically every character from A to Z and a to z and 0 -9 and some other special characters have respective numeric values associated with them,

For example A is 65 in ASCII, but this is good enough for english language considering limitations of usage of some special characters, if we would like to add some other language, these characters should also have some numeric values for encoding and this is achieve by UTF-8

UTF-8 is just one of the encoding methods that were invented to implement this requirement. It lets you write text in all kinds of languages, so French accents will appear perfectly fine, as will text like this

To display an HTML page correctly, a web browser must know which character set (character encoding) to use.

What is the difference between static and dynamic web pages ?


#CSS Questions: 
What is responsive web design ?
Responsive web design aims to fit website in all the screen sizes with respect to device width

 
How do you apply style using javascript ?
What are the various display properties ?
Difference between SVG and Canvas ?
Difference between block level vs Inline Elements ?
What are psedo: selectors ?
What are all the aspects of responsive web design ?

What do you use for responsiveness in your app ?
What is flexbox ?
How to do you know the Device width on which app is shown ?
How do you differentiate a touch based vs non touch based devices ?
How do you customize bootstrap before you start development ?
Why do we use pre processors ?

Other Places to look for more questions:

Work Environment Questions:
What is your general git workflow ?
How is your team size ?
What is your typical work day look like ?
What are you expecting in your new job ?
Are you more of a Developer/Designer/Backend person, which one you prefer and why ?
What is biggest challenge you faced in your development and what did you do to overcome it ?
Is there anything you build that you are proud of telling others ?


#Nodejs

What are the features of Nodejs ?
What is the Architecture of Nodejs ?
Have you used Nodejs in your application ?
What middlewares have you used in Nodejs ?
What is callback hell ?

#JQuery






Question: 
<div>Java</div>
<div>C++</div>
<div>C#</div>
<div>HTML</div>
<div>CSS</div>
when we click on any div tag do the following using javascript/jquery
1. Print the innerText of clicked div in a alert box (eg:- you have clicked on “C++”) 
2. Change the background color of clicked div to blue.
3. Reset the background color of the all divs.
Note:- Don't modify the HTML

Answer: 

<!DOCTYPE html>
<html>
<head>
<title>Try jQuery Online</title>
<script src="//ajax.googleapis.com/ajax/libs/jquery/2.1.1/jquery.min.js"></script>
<script>


$(document).ready(function() {
   $("div").click(function(e){ 
       console.log(e.target.innerHTML)   // Print the innerText of clicked div in a alert box
       if(e.target.style["background-color"] == "blue"){ 
           e.target.style["background-color"] = "white"
       }else{
           e.target.style["background-color"] = "blue" // Change the background color of clicked div to blue
       }
   })

$("div").css( "background-color", "white" ) // Reset the background color of the all divs.
});





</script>
</head>
<body>
    <div>Java</div>
    <div>C++</div>
    <div>C#</div>
    <div>HTML</div>
    <div>CSS</div>
</body>
</html>





<form id=“loginForm” action=“auth.jsp”>
<input type=“text” id=“username” /> <br/>
<input type=“password” name=“password” /> <br/>
<input type=“button” value=“Login” id=“login_button”/><br/>
<div>Your username is:<label id=“username_label”></label></div>
</form> 
1. Dynamically Set the value of password field to “Welcome”
2. Onchange event of username text box read the value and print in the label 
3. onclick of login button submit the form

Note:- 1. You can use Javascript/jQuery
2. Don't modify the HTML

ComponentWillMount
Is called when component is about to be unmounted from DOM

