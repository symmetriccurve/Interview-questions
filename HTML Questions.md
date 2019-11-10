### New HTML5 tags ?

---

### What does HTML action attribute does ? What happen when it is not defined ?

---

### What is the difference between the HTML attribute and DOM property ?

---

### Javascript,CSS can be added via CDN and local files, which one do you prefer ?

---

### The function appendChildren should add a new child div to each existing div. The new divs should be decorated by call decorateDiv.

### For example, after appendChild is executed, the following divs:

```javascript
<div id="a">
	<div id="b">
	</div>
</div>
```

### should take the following form (assuming decorateDiv does nothing):

```javascript
<div id="a">
	<div id="b">
		<div></div>
	</div>
	<div></div>
</div>
```

### The code below should do the job, except that for some reason it goes into an infinite loop. Fix the bugs.

```javascript
    function appendChildren(decorateDivFunction) {
      var allDivs = document.getElementsByTagName("div");
      for (var i = 0; i < allDivs.length; i++) {
        var newDiv = document.createElement("div");
        decorateDivFunction(newDiv);
        allDivs[i].appendChild(newDiv);
      }
    }

    appendChildren(function(div) {});
```

appendChildren is a recursive function and calls recursively until allDivs.length is less than i which never happens as function keep adding the div recursively. 

The fix is to isolate the allDivs variable and hold the initial values without being updated someway, or instead of getting the updated html divs, we can get the querySelectorAll instead of getElementsByTagName so we only get the divs from the first iteration avoiding the loop

A quick fix is to 

```javascript
function appendChildren(decorateDivFunction) {
  var allDivs = document.querySelectorAll("div");
  for (var i = 0; i < allDivs.length; i++) {
     var newDiv = document.createElement("div");
     decorateDivFunction(newDiv);
     allDivs[i].appendChild(newDiv);
   }
}

  appendChildren(function(div) {});
```

