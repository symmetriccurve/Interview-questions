### Do you have a situation where you disagreed with the team ?

The reasoning behind this question is to understand how do you react to people who disagree with you, Do you simply quit the job ? or stick along with the wrong decision(in respect to you) and get back to the work.

A lot of times I witnessed experienced developers argue/debate/disagree over patterns again and again, and prove that how their proposed pattern is much cleaner and easier(in terms of understanding and implementing) than others.

*A pattern is nothing but a particular way/process to accomplish(code) a thing(feature). 
(This pattern I am talking about is not related to design pattern)*

Example: 

[if you ask me to start a fire without matches](https://www.artofmanliness.com/articles/9-ways-to-start-a-fire-without-matches)

I can choose any of the above ways, all of which have pros and cons. 

Few other common disagreements are around which libraries/tools to be used if this is the first time the company adopting new tool/library. The least discussions happen over naming conventions and folder structures.

*My Answer:*

I was involved in a application to upgrade dependency versions to latest and increase the performance of the application, the application was build using older versions react and bower dependencies. Few parts of the application used JQuery(the reason the application was slow) and most of it was React. I cleaned up the Jquery part and written equivalent re usable react components. I also added babel into the project hoping I would convince the other developers on start using latest ES6 features.

This was a legacy project and major functionalities are coded by one of the very senior developer of the company using available [react v0.14.4](https://github.com/facebook/react/releases?after=v15.0.0) back in 2016 when react was not that popular. 

There were 6 developers( including me ) in the team and I was able to convince all other developers to start using the ES6 features which can cut down code, but the a senior developer disagreed to say that this will add additional unnecessary complexity in to the project and may have obscure implications so we better stick to the ES5. It took me a week to have prototypes/presentations on how we can better destructure, use arrow function, spread operators and other features of the ES6, but I terribly failed to convince him that this enhances the developer experience and cuts downs number of lines of code. 
(I brought this up the product owner, but I failed to answer how this brings value to the product since he says developer experience does not count towards the product value) 

I removed the babel integration and sent a PR(Pull Request), he added few comments on the JQuery converted to "ES5 react components", I added the changes accordingly and continued to upgrade the versions and moved all the bower dependencies to npm dependencies. 


A follow up question would be, 
**How did you feel about this ?** or 
**How long did you work after this incident ?**

*My Answer:*

I think, may be he was right, since he build a lot of functionalities of the component, It might be harder for him to switch the gears in an production environment, he would definitely add a cognitive load on some one who have not used ES6 previously. I worked over an year with the team and I build a lot of my javascript skills based on the code comments from the very same senior developer. :D 

---

### What are the few things you look for when you review another developer's code ?
I look for code consistency✅, reusability📦 and readability📖 of the code. I focus more on readability and maintainability📁 of the code on top of anything else, I strongly believe a well written code is nothing more than a well maintainable code. 

Few other things I look for is CONSTANTS, let's say I am reviewing the code of the developer who written a function to enable **Place Order** button only if minimum amount of order is met, he can simply if( cartTotal > 50 ), 

For a new developer🐣 who is reading through this code, he has no clue about this magic number(50) appear from no where🙇, I always insist in creating a constants file and have constant something like const MINIMUM_ORDER_TO_SHIP = 50 👏 then use the constant.

if( cartTotal > MINIMUM_ORDER_TO_SHIP) 👍 makes the easier to read and maintain🎉, if the company decides to make changes to minimum order, I don't have to dig⚓️ through the files to find this if loop to alter the minimum order to ship, rather I would looks for constants file and make the changes accordingly.

Few other things I look for are
* Indentation
* Naming conventions 
* Code comments if the block of code has any edge case(Example: like if a coupon is applied, then no minium order is required)

---

### What do you enjoy, to be a developer or to be a manager ?
I enjoy being a developer more, not only I code for work but for fun. I enjoy learning new things and put my learnings into implementation. Being developer gives me a sense of accomplishment every time I build something new 👏🎯. 

I am not sure If I would feel more accomplished making power point presentations 🙈!!! Just Kidding !! 😝😁

---

### How do you keep up with the technologies ?
I think there is no other industry that is changing as rapidly as software development😭. I set aside at-least 30 minutes 🕔 🕠 of my time to keep up to date with the technologies. 

I avidly follow 🐶[hacker news](https://news.ycombinator.com/) for all my tech updates, each news link takes to different websites. 

I look at [stackoverflow]( https://stackoverflow.com/?tab=week) top questions🔥, I also love to read popular medium stories from the developers from top tech companies.

and yeah, I also catch up with 🎶 🎵[podcasts](https://softwareengineeringdaily.com) if I am sick of reading 😅.

---

### What is that you build that you are proud of ? 💪
The answers are subjective 🙌

My answer: 
I build a [mine-sweeper](https://github.com/symmetriccurve/minesweeper-with-react)💣 from the scratch using reactjs ⚛.

Few other things,
1. I coded a python script that scans through the directory structure of react project and adds unit test templates to start with
2. My [portfolio](https://www.belvikram.com)

---

### If given a chance to re write your current application, what are the few things that you would do differently now ?

1. I would restructure the folder structure📂 in whole different way than that exists now. With the current structure📁, as we started to add more features ✨, the more nested the folder structure is😭. I would do more flatten structure🍞 this time😅
2. I will decouple most of the components on the basis of view💄 and logic🧠 and have more smaller reusable components🧩.

---

### what do you dislike in your current project, what can you do to make it better ?
My current project is re-write of a legacy application🌚 which was build like 7 years back using jQuery👴🏼. When we started to rewrite the components and stitch🧵 the logic, we were not sure about the all the use cases possible . The unit tests💼 were out of sync and does more implementation testing than testing the functionality, and also there is bare minimum documentation📄 available on the requirements. 

It takes a lot of time on running back and worth with the QA team as we progress to check if everything matches the parity.

I believe the quote by Edward V. Berard — `Walking on water and developing software from a specification are easy if both are frozen.`

This constant check with QA team was setting back the team in terms of development🧪, as we think we are getting closer to close the story, there comes another corner use case we missed.

Learning from this, we are trying our best to create documentation📄 around the application as we build and focus adding more unit tests💼 testing the functionality🧪.

---

### is there any time you under estimated a story ? and how did you handle the situation ?

--- 

### What is your idle work environment ?
### How do you envision your next role should be ?
### What are you looking for in your next position ?

--- 

### If you have limited time to deliver 11 features for a application and you see you can only do 5 features, How will you able to handle this deadline situation ?

---
### What is most complex piece of development you did so far ?

---
### Do you like to work isolated or with a Team ? why ?

---
### Is there a situation you asked help from the team ? How do you ask help from the team ?

---
### What is something you learned in your current project that can help you to do better in your next project ?


