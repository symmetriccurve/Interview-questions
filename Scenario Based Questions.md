### How do you determine if a network call failed based on status code ?

##### Scenario

---

### What is cors issue ? How did you resolve it ?

##### Scenario

---

### You are put in to a legacy code base and ask for a strategy to start refactoring ? Where will you begin with ?

##### Scenario

---

### Do you think which is important for a product, UI implementation or UX experience ?

##### Scenario

---

### if there are 4 different web apps of a single company have four different businesses, do you think the UI should look same across all 4 apps or since type of business is different should they look different ?

##### Scenario,UX

---

### When you build a application from scratch, can you do better if you know all the upcoming features ahead of time or do you like to know just about the feature you are building and know extra featured as business comes along ? which way you prefer and why ?

##### Scenario

---

### Talk about how do you get requirements ?

Whenever there are new requirements coming up in the business, initially product owners sit with the designers and discuss on the designs and later they set up a meeting with developers and present all the prototypes those are designed. Once the presentation is done, if developers have any questions or change in the designs based on the implementation they discuss with the team and make necessary changes if needed.

##### Scenario

---

### Bit about Development process ? how long is a Sprint ?

The sprint is two weeks long, which starts with the sprint planning. In sprint planning the stories which are already groomed and estimated are assigned to developers. Grooming sessions are usually done in mid of the sprint and any questions on the stories will be cleared during this meeting and if there are any blockers then that story remains in backlog and won’t pull into the the active sprint.

##### Scenario

---

### How does your code review process look like?

Once the PR is raised, before reviewing the code, the reviewers wait on the checks to pass. Main Checks include the test cases and the code quality gate. As part of the development unit testing is most important and test cases are also pushed into git along with the actual implementation part. And maintaining the code standards as per the organization is important for easy debugging and also it will be easy for any new members join in the team.

##### Scenario

---

### Explain about Git branching process in your project?

Each and every developer has to create their own branches and work on it locally. Once it’s pushed to git, it will be reviewed and approved by at least 2 reviewers, then it can be merged to the main branch(master branch depending on each project branching setup).

##### Scenario

---

### Talk about your development environments ?

As part of the development, analyzing the story and getting clarified on all the questions is important. Then development work will be started, any new feature that’s developed has to be feature flagged. So that if there’s any issue in the implementation then the feature flag can be simply turned off instead reverting the entire code back. Later unit test cases are written and the scripts are run. Once all the test cases are passed, then need to check on code standards and finally merged to the master

##### Scenario

---

### What happens at the end of the sprint ?

Once the sprint is done, then there will be a demo that has to be given to managers. All the new features developed as part of the sprint are demoed. And once everything looks good, then it will be deployed to prod.

##### Scenario

---

### How frequent are your releases ?

Every sprint is a prod release in our project and before going to prod, initially the new feature will be deployed to dev environment and then after validation its deployed to stage. And finally if everything looks good on stage then it’s deployed to prod finally.

##### Scenario

---

### Have you got any experience bringing up to speed for a new developer on the team ?

If there are any new members joined in the team, initially KT sessions are given to them. In those KT sessions most of the information about the business flow, Architecture, tech stack and team structure will be given to them. For code standards, we created a confluence page. The new team members can go through that page for standards and folder structure that has to be followed.

##### Scenario

---

### It’s over a year you are working from home, what do you thing have changed in terms of communication with team ?

Since there are no more meeting rooms, zoom meetings are the best option for any type of quick questions. especially during the production deployments, we had all day zoom meetings in order to work on the hot fixes that has to be released to prod.

##### Scenario

---

### Talk to me about your proudest moment as an Engineer?

Implementing Micro-front ends are the best proudest moment. There are several pages in application where we we segregated it into different sub applications and all the sub applications are supposed to run in order to run the main application and it’s bit complicated to work on such applications, since whenever there’s a new code, in order to keep all the sub apps up to date, We need to pull the code on all the sub apps, but it reduces the deployment time. And no need to stop the deployment process when there’s issue on the another page. Also it will be easy to detect where there’s an issue and fix it immediately.

##### Scenario

---
### What steps do you take to make sure that your changes won't impact other people's work?

Each scenario is different when in case if I am new the product, I will heavily rely on the unit tests and automation to capture it, in cases there are no unit tests or automation, I would share a sandbox URLs to other devs and take help from already existing devs to code review my changes, but having unit tests is 100% guarantee that I am not breaking anything, if they do not exist I would at least try to add some around the feature that I am integrating. 

##### Scenario

---

### What steps do you take when you are working with a new tech you are not familiar with?
I am more of a person prefer the code over the documentation, but don’t get me wrong. Documentation is good, but code helps me understand the implementation better and quickly learn. My approach I guess is pretty straight forward like I will google on why this technology exists and why problems does this solve then google every single keyword to get the fundaments right before the complex stuff, then create a small prototype based on my understanding. Make few recording as a reference material to quickly look for keywords and usage.. then obviously stack overflow is way to go.

##### Scenario

---

##### Tell me about a time where you had finished all your work ?
Usually I plan my sprint good enough depending on the complexity of the projects but there are certain instances where this happens, in those situations I try to help the other team mates to finish up there work or try to dig through the code and find any code improvements and spin tickets based on my finding, I would not fix them right away but create tech debt tickets with details to bring them in when we have capacity.

##### Scenario

---

##### What do you do when you have a lot on your plate and someone helps you for help ?
It depends on the situation, I will try to prioritise based on the urgency. Imagine I am building a new feature and someone come to me to help on a production issue, I would jump right on. But imagine if a dev is asking help for fixing an environment issue local to his machine, I would give him directions and move on with my stuff. So, it certainly depends.

##### Scenario
---

##### Tell me about a time where you made a mistake, how did you overcome it?
There was a situation when I had to create a Carousal component, I estimated to be a 3 pointer story but later ended up spending like 2 whole weeks. I badly underestimated the story as I thought how hard it can be to make a carousal component, but there was a catch that not all the carousal components are of same size, basically they were images consumed from social media networks, these come in different sizes. That was one part of the challenge and another part was the accessibility is breaking as carousal should also be accessible with keyboard, I turned it in 3 days but spent like 2 more days fixing it and then I finally re-implemented it from the ground up with a different CSS transform approach. 

##### Scenario
---

##### Tell me about a time you saw inefficiencies or problems, what steps do you take to fix them?
Certainly not problems not I would say more of less optimised ways to do the stuff, mostly around the bundling and deploying process. Usually I would create a prototype on how this can be improved, the prototype helps me do 2 things at the same time. It gives me confidence that this can certainly be done and it helps to show the numbers how we can improve this. For example, the last project I worked with had a build time of 52 minutes and close to 25 minutes were spent on the unit tests, I introduces the parallel unit testing with Jenkins job running multiple job and then collect the coverage from various AWS instances and the unit testing dropped to 8 minutes, that is like 52 minutes to 35 minutes straight.

##### Scenario
---

##### What does your ideal role look like?
My ideal role is build tools that helps the other developers to move faster, I wanted to part of a horizontal team that helps to provide all the tooling required by the other teams to improve their velocity. It also helps me learn from multiple consumers of this tools/libraries. 

##### Scenario
