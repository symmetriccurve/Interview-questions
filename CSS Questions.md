### How to put a div in the center of the screen ? 

---

### Can you explain different position properties in CSS

---

### What is box modal ?

---

### What is margin collapse ?
https://css-tricks.com/what-you-should-know-about-collapsing-margins/

When two block level elements lets says blockA and blockB are stacked one above the other and 
blockA have margin-bottom of 50px;
blockB have margin-top of 100px;

the margins of blockA and blockB elements are collapsed and have only have 100px space between them(margin with higher number)

Collapse margins only happens
- on top and bottom margins(Vertical margins)
- with block elements
- if the elements are in direct contact with out any padding and border in between. 

https://jsfiddle.net/bevikram/fr8aogqb/

---

### What to disable margin collapse ?
Margin collapse only happens with block level elements, applying `display: inline-block` disables the margin collapse.

---

### What does margin collapse exist?
### is there a use case for margin collapse ?
Margin collapse is useful when dealing with typographic elements like h tags, p tags. 

The collapse helps to better formate the elements 
https://medium.com/@joseph0crick/margin-collapse-in-css-what-why-and-how-328c10e37ca0

---

### How do you structure your stylesheets ?

---

### Are you familiar with BEM (Block Element modifier) ?

---

### What are pseudo classes in CSS ?

---

### What are pointer events ?

---

### What is the difference between display:none and display:hidden ?

---

### What is flex box ?

---

### How do you vertically and horizontally align items inside a div ?

----

### What is the difference between padding and margin ?

--- 

### Explain media queries ?

---

### What is your approach developing screen, do you first target larger screens or smaller screen ?

---

### What is accessibility ?

---

### What do you understand by responsive design ?

---

### How do you collaborate with UI/UX team ?

--- 

### What is a pre-processor ?

---

### Are you familiar with Sass/Scss ?

---

### Difference between SVG and Canvas ? 

---

### Difference between block level vs Inline Elements

---

### What are pseudo: selectors ?

---

### How to do you know the Device width on which app is shown ?

---

### How do you differentiate a touch based vs non touch based devices ?

---

### In terms of responsive web application, which approach do you use, min-width or max-width ?

---

### What are the benefits of flex-box other than responsiveness ?

---

### What does it mean when I say flex: 1 1 20px?

---

### Which style is effective, when a style object is both inside the media query and outside the media query?

---

### How div are aligned if I do inline-block and width 50% on both elements ? Do they wrap, if so why ?

---

### What CSS combinator do you if you have to select direct child of a parent ?

---

### What CSS combinator do you if you have to select adjacent siblings inside a parent?

---

### Why do you use box-sizing property ?

---

### Do you know about css clearfix ?
CSS clearfix is a hack to make the element larger to fit all of it's floating children

Let says A parent element div has 10px height and have few children
first child div has 20px height and
second child div has 40px height.

the child div overflow out of parent div, to fix this a clearfix is applied to parent div to expand and fix all of it's children.

https://stackoverflow.com/questions/8554043/what-is-a-clearfix

---

### Difference between CSS and CSS3 ?
| CSS  |  CSS3 | 
|---|---|
| No rounder corners  | Achieved using border-radius  |
| No Gradients |  Achieved using background: linear-gradient(white,black) |
| No Animated effects, achieved using JQuery or javascript  | inbuild animation effects like shadow and animation interval etc  |
| Only support for web safe fonts| Access to more designer fonts  |
| Does not have modules - hence slow | Has modules - is faster |

https://www.upwork.com/hiring/development/css-vs-css3/

---

### Difference between CSS and CSS3 ?
