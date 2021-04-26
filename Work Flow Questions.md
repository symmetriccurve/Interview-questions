#### Do you have a situation where you disagreed with the team ?

The reasoning behind this question is to understand how do you react to people who disagree with you, Do you simply quit the job ? or stick along with the wrong decision(in respect to you) and get back to the work.

A lot of times I witnessed experienced developers argue/debate/disagree over patterns again and again, and prove that how their proposed pattern is much cleaner and easier(in terms of understanding and implementing) than others.

_A pattern is nothing but a particular way/process to accomplish(code) a thing(feature).
(This pattern I am talking about is not related to design pattern)_

Example:

[if you ask me to start a fire without matches](https://www.artofmanliness.com/articles/9-ways-to-start-a-fire-without-matches)

I can choose any of the above ways, all of which have pros and cons.

Few other common disagreements are around which libraries/tools to be used if this is the first time the company adopting new tool/library. The least discussions happen over naming conventions and folder structures.

_My Answer:_

I was involved in a application to upgrade dependency versions to latest and increase the performance of the application, the application was build using older versions react and bower dependencies. Few parts of the application used JQuery(the reason the application was slow) and most of it was React. I cleaned up the Jquery part and written equivalent re usable react components. I also added babel into the project hoping I would convince the other developers on start using latest ES6 features.

This was a legacy project and major functionalities are coded by one of the very senior developer of the company using available [react v0.14.4](https://github.com/facebook/react/releases?after=v15.0.0) back in 2016 when react was not that popular.

There were 6 developers( including me ) in the team and I was able to convince all other developers to start using the ES6 features which can cut down code, but the a senior developer disagreed to say that this will add additional unnecessary complexity in to the project and may have obscure implications so we better stick to the ES5. It took me a week to have prototypes/presentations on how we can better destructure, use arrow function, spread operators and other features of the ES6, but I terribly failed to convince him that this enhances the developer experience and cuts downs number of lines of code.
(I brought this up the product owner, but I failed to answer how this brings value to the product since he says developer experience does not count towards the product value)

I removed the babel integration and sent a PR(Pull Request), he added few comments on the JQuery converted to "ES5 react components", I added the changes accordingly and continued to upgrade the versions and moved all the bower dependencies to npm dependencies.

A follow up question would be,
**How did you feel about this ?** or
**How long did you work after this incident ?**

_My Answer:_

I think, may be he was right, since he build a lot of functionalities of the component, It might be harder for him to switch the gears in an production environment, he would definitely add a cognitive load on some one who have not used ES6 previously. I worked over an year with the team and I build a lot of my javascript skills based on the code comments from the very same senior developer. :D

##### Scenario

---

#### What are the few things you look for when you review another developer's code ?

I look for code consistency✅, reusability📦 and readability📖 of the code. I focus more on readability and maintainability📁 of the code on top of anything else, I strongly believe a well written code is nothing more than a well maintainable code.

Few other things I look for is CONSTANTS, let's say I am reviewing the code of the developer who written a function to enable **Place Order** button only if minimum amount of order is met, he can simply if( cartTotal > 50 ),

For a new developer🐣 who is reading through this code, he has no clue about this magic number(50) appear from no where🙇, I always insist in creating a constants file and have constant something like const MINIMUM_ORDER_TO_SHIP = 50 👏 then use the constant.

if( cartTotal > MINIMUM_ORDER_TO_SHIP) 👍 makes the easier to read and maintain🎉, if the company decides to make changes to minimum order, I don't have to dig⚓️ through the files to find this if loop to alter the minimum order to ship, rather I would looks for constants file and make the changes accordingly.

Few other things I look for are

- Indentation
- Naming conventions
- Code comments if the block of code has any edge case(Example: like if a coupon is applied, then no minium order is required)

##### Work Flow

---

#### What do you enjoy, to be a developer or to be a manager ?

I enjoy being a developer more, not only I code for work but for fun. I enjoy learning new things and put my learnings into implementation. Being developer gives me a sense of accomplishment every time I build something new 👏🎯.

I am not sure If I would feel more accomplished making power point presentations 🙈!!! Just Kidding !! 😝😁

##### Work Flow

---

#### How do you keep up with the technologies ?

I think there is no other industry that is changing as rapidly as software development😭. I set aside at-least 30 minutes 🕔 🕠 of my time to keep up to date with the technologies.

I avidly follow 🐶[hacker news](https://news.ycombinator.com/) for all my tech updates, each news link takes to different websites.

I look at [stackoverflow](https://stackoverflow.com/?tab=week) top questions🔥, I also love to read popular medium stories from the developers from top tech companies.

and yeah, I also catch up with 🎶 🎵[podcasts](https://softwareengineeringdaily.com) if I am sick of reading 😅.

##### Work Flow

---

#### What is that you build that you are proud of ? 💪

The answers are subjective 🙌

My answer:
I build a [mine-sweeper](https://github.com/symmetriccurve/minesweeper-with-react)💣 from the scratch using reactjs ⚛.

Few other things,

1. I coded a python script that scans through the directory structure of react project and adds unit test templates to start with
2. My [portfolio](https://www.belvikram.com)

##### Work Flow

---

#### If given a chance to re write your current application, what are the few things that you would do differently now ?

1. I would restructure the folder structure📂 in whole different way than that exists now. With the current structure📁, as we started to add more features ✨, the more nested the folder structure is😭. I would do more flatten structure🍞 this time😅
2. I will decouple most of the components on the basis of view💄 and logic🧠 and have more smaller reusable components🧩.

##### Work Flow

---

#### what do you dislike in your current project, what can you do to make it better ?

My current project is re-write of a legacy application🌚 which was build like 7 years back using jQuery👴🏼. When we started to rewrite the components and stitch🧵 the logic, we were not sure about the all the use cases possible . The unit tests💼 were out of sync and does more implementation testing than testing the functionality, and also there is bare minimum documentation📄 available on the requirements.

It takes a lot of time on running back and worth with the QA team as we progress to check if everything matches the parity.

I believe the quote by Edward V. Berard — `Walking on water and developing software from a specification are easy if both are frozen.`

This constant check with QA team was setting back the team in terms of development🧪, as we think we are getting closer to close the story, there comes another corner use case we missed.

Learning from this, we are trying our best to create documentation📄 around the application as we build and focus adding more unit tests💼 testing the functionality🧪.

##### Scenario

---

#### is there any time you under estimated a story ? and how did you handle the situation ?

##### Scenario

---

#### What is your idle work environment ?

##### Scenario

---

#### How do you envision your next role should be ?

##### Work Flow

---

#### What are you looking for in your next position ?

##### Work Flow

---

#### If you have limited time to deliver 11 features for a application and you see you can only do 5 features, How will you able to handle this deadline situation ?

##### Work Flow

---

#### Do you have experience deploying applications in Azure? Which role did you do this in?

I have experience deploying the applications in Azure with the help of few backend developers. I am not primarily the contributor role.

##### Work Flow

---

#### What cloud technologies have you used or are using now?I am familiar with Google Cloud, AWS, Firebase

(Google owned). Currently we are using Microsoft Azure.

##### Work Flow

---

#### Tell Us about a Challenge/Problem you recently faced on a project ? How did you approach solving it and what was the outcome ?

While I was working on my current project, as part of the video player integration I had to play a video file downloaded from a remote server, as the this was part of a migration project from jQuery to react, I took the part of the feature which involved integrating a web video player, to be honest I thought this was not complex initially as I did my research on the available libraries to play the video.. When I started integrating the video player with the sample video of same format I was able to play the video without a hitch but when I am trying to download the video from the URL the video player fails to load the video, my initial thoughts were the player is  not capable of playing a stream as it is downloading so I used a lazy loading view to completely download the video and then play it, still the player was not able to pick the steam and throws incompatible video format even though i am 100% sure the video format I am using is supported by the player.. But I had no clue what I was doing wrong and I could not find a related issue on the github repo where the player is hosted.. I switched to different players just to understand if the issue is with the player with the video being downloaded, I was unable to play the video in any available video players(not even on videojs which can play around 90% of the video formats). I ran out of options and I chose to use the existing JQuery video player though the library is deprecated and did not have an option to play the video at 1X, 2X, 5X playback speed which is the new requirement. Interestingly I was not able to play the video in the JQuery player, I dug through the huge code base and finally found that under the hood, the video codec has been altered after the video is downloaded to support it to play on the web player… all i had to do is to add a few params to the h264 video codec to merge audio and video before it is handed to the video player.. Finally I was able to run the video on the Videojs player with playback speed. I really leart about video formats and codec with this integration.

##### Work Flow

---

#### What is most complex piece of development you did so far ?

##### Work Flow

---

#### Do you like to work isolated or with a Team ? why ?

##### Work Flow

---

#### Is there a situation you asked help from the team ? How do you ask help from the team ?

##### Work Flow

---

#### What is something you learned in your current project that can help you to do better in your next project ?

##### Work Flow

---

### Why React is better than other libraries ?

##### Work Flow

---

### What unit testing libraries you have used ?

##### Work Flow

---

### What is the greatest achievement in your project that received appreciation ?

##### Work Flow

---

### Tell me about your recent project ?

##### Work Flow

---

### Do you have experience with Java ?

##### Work Flow

---

### What is the difference between git rebase and git merge ?

Git Rebase re-plays the commits of branch on top of the base branch by pointing the base to the new updated base and adding commits on top the new base so basically forward the head and then apply the changes but on the other hand git merge add the commits

##### Work Flow

---

### Is there a situation where you went above and beyond to get work done ?

##### Work Flow

---

### Do you merge your code directly to the master ?

When a new task is picked by a developer, he or she creates a new branch based off of develop branch with proper branch naming convention depending on whether it is fix or feature or hotfix etc appended with ticket number to help us to track back why this PR is created.After we complete the code work on the branch, we update tests, documentation etc depending on what we are changing and send a PR and tag the PR with initial review so it is reviewed by peer developers, once at-least 2 peer developers approve the PR we re tag the PR for ‘need final review’ which is reviewed by senior developers and leads.Once the PR is on the develop branch a jenkins job triggers updating the version number and deploys to the development environment, where we validate our changes and send over the fix to the QA team to quick validate on high level.. once we have the QA approval we move the ticker for ready for QA which is tested as part of regression when we make weekly releases.

##### Work Flow

---

### What is the release cycle you follow ?

##### Work Flow

---

### What is remote debugging on Java on eclipse ?

##### Work Flow

---

### if you do hot replace on java instance, how long does the code lasted ?

##### Work Flow

---

### if you hot replace, will it override the classes immediately ?

##### Work Flow

---

### What happens if I restart the instance on remote debugging ?.

##### Work Flow

---

### What happens when you are struck, what do you do ?

##### Work Flow

---

### What did you do if you worked on a feature and some other developer sent a PR to your code base as an improvement ?

##### Work Flow

---

### Can you describe me a scenario where you were working on a bug and found that bug is caused by some other team completely unrelated to your team, how will you tackle this ?

##### Work Flow

---

### How many team members ? how large of a team can you think you can do better ?

##### Work Flow

---

### We do not have a defined set of requirements, you need to get the requirements, we do not have a BA to get you requirements ? How comfortable are you working independently ?

##### Work Flow

---

### Tell us about a position where you were doing more than one job like Developer and Designer or Scrum master and Developer ?

##### Work Flow

---

### What makes a really good UX design ?

##### Work Flow

---

### Have you ever had a conflict with UX designer ?

##### Work Flow

---

### Do you like to build the components from the scratch or use third party libraries ?

##### Work Flow

---

### Have you ever contributed in to a common component library or worked with a factory team to provide common tools/libraries to other team?

##### Work Flow

---

### What do you think of Agile methodology ?

##### Agile

---

### How long is your sprint ?

##### Agile

---

### Did you ever underestimated a user story ? How did you handle it ?

##### Agile

---

### If you have build 7 features by the end of the sprint deadline and you can only build 4 of them, how do you communicate this to the scrum master or product owner ? or will you put extra hours to complete all the 7 features ?

##### Agile

---
