### When do you use a FlatList vs ScrollView ?

It depends on the requirement, if I have defined list of item that has to be loaded all at once or all rows should be rendered in that case I would use a ScrollView. But, in cases where I have lot of rows and I do have to render them all at once and only render them when user starts scrolling then I can use a FlatList.

In terms of performance, FlatList wins the race as it renders only items which are visible on the screen. When we are scrolling, it renders the items which about to be shown. Also, it removes the items outside the screen, when we were scrolling away.

Those qualities of the FlatList make it more performant.

On top of that, the component also provides some other features such as header and footer support, pull to refresh functionality etc.

##### React Native

---

### How do you make sure not to block the UI when you are making the API calls ?

The network requests do not block the UI thread, though we use Fetch or Axios using javascript to make the API request, under the wood those requests are performed in separate threads in Objective C or swift on iOS and java on Android and as UI thread never get blocked as it is a separate platform thread.

Learn more: https://www.youtube.com/watch?v=8N4f4h6SThc&t=8m40s&ab_channel=ReactiveConf

##### React Native

---

### This is going to a subjective, feel free to say what do you think ? user makes a product purchase by hitting the checkout button and it takes close to 4-5 seconds until all the process is complete and show a order confirmation page. Can you think of some way to make use of this 5 seconds instead of showing boring spinner yet not redirecting to any other page ?

##### React Native, Scenario

---

### Are you familiar with code signing on iOS and Android ?

##### React Native, Scenario

---

### Can you talk to me a little about CI/CD pipeline on React Native ?

##### React Native

---
