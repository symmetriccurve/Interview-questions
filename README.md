# Interview-questions

MOST ASKED QUESTION IN EVERY INTERVIEW  are marked as M next to question.

React
What do you understand by Component Life Cycle in React ? (M)
Why to use React if there are so many frameworks available in the market ?

Javascript


CSS

General UI

WorkRelated




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

