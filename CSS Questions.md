### How to put a div in the center of the screen ?

- Approach 1:
  `margin: 0 auto;`

Do not forget to add the width of the element, `margin: 0 auto` only works with defined widths

- Approach 2:
  By Positioning absolute and adding top and left margins to 50% accounting the height and width of the element and applying negative margin.

Example style object:

`position: absolute; width: Ypx; height: Xpx; z-index: 15; top: 50%; left: 50%; margin: -X/2 px 0 0 -Y/2 px;`

- Approach 3:
  Applying display flex and align-items and justify-content to center

Example style object:

    `display: flex;
    align-items: center;
    justify-content: center;`

- Approach 4:

The simplest of all is to apply `text-align-center` to the wrapper element and `display:inline-block` to inner elements

##### CSS

---

### Difference between block and inline-block ?

##### CSS

---

### Can you explain different position properties in CSS ?

There are five different position values:

(How do I remember:
Mnemonic: Frass
Meaning: `fine powdery refuse or fragile perforated wood produced by the activity of boring insects` )

- Static

  - Element is positioned with normal flow of page.
  - left/right/top/bottom/z-index set then there will be no effect on that element.

- Relative

  - Element is positioned with normal flow of page.
  - left/right/top/bottom/z-index will move the element accordingly.

- Absolute

  - Elements dis respect normal flow of page
  - Element is positioned absolutely to its first positioned parent

- Fixed

  - Behaves as a Absolute positioned element
  - Positioned with respect to browser window
  - Example: Chat window's

- Sticky
  - Element is positioned based on the user's scroll position
  - Example: Excel sheet fixed row headers.

##### CSS

---

### What is box modal ?

##### CSS,Frequently Asked

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

##### CSS

---

### What to disable margin collapse ?

Margin collapse only happens with block level elements, applying `display: inline-block` disables the margin collapse.

##### CSS

---

### What does margin collapse exist?

### is there a use case for margin collapse ?

Margin collapse is useful when dealing with typographic elements like h tags, p tags.

The collapse helps to better formate the elements
https://medium.com/@joseph0crick/margin-collapse-in-css-what-why-and-how-328c10e37ca0

##### CSS

---

### How do you structure your stylesheets ?

##### CSS

---

### Are you familiar with BEM (Block Element modifier) ?

##### CSS

---

### What are pseudo classes in CSS ?

##### CSS

---

### What are pointer events ?

##### CSS

---

### What is the difference between display:none and display:hidden ?

##### CSS,Frequently Asked

---

### What is flex box ?

##### CSS,Frequently Asked

---

### How do you vertically and horizontally align items inside a div ?

##### CSS

---

### What is the difference between padding and margin ?

##### CSS

---

### Explain media queries ?

##### CSS

---

### What is your approach developing screen, do you first target larger screens or smaller screen ?

##### CSS,Frequently Asked

---

### What is accessibility ?

##### CSS

---

### What do you understand by responsive design ?

##### CSS,Frequently Asked

---

### How do you collaborate with UI/UX team ?

##### CSS,Frequently Asked

---

### What is a pre-processor ?

##### CSS

---

### Are you familiar with Sass/Scss ?

##### CSS

---

### Difference between SVG and Canvas ?

##### CSS

---

### Difference between block level vs Inline Elements ?

##### CSS

---

### What are pseudo: selectors ?

##### CSS

---

### How to retrieve the device width ?

##### CSS

---

### How do you differentiate a touch based vs non touch based devices ?

##### CSS

---

### In terms of responsive web application, which approach do you use, min-width or max-width ?

##### CSS

---

### What are the benefits of flex-box other than responsiveness ?

##### CSS

---

### What does it mean when I say flex: 1 1 20px?

/_ Three values: flex-grow | flex-shrink | flex-basis _/
https://developer.mozilla.org/en-US/docs/Web/CSS/flex

##### CSS

---

### Which style is effective, when a style object is both inside the media query and outside the media query?

if the device matches the media query, the media query is effective or else the outside the media query style object is effective.

##### CSS

---

### How div are aligned if I do inline-block and width 50% on both elements ? Do they wrap, if so why ?

##### CSS

---

### Is it possible to put CSS @media rules inline?

No, @media rules and media queries cannot exist in inline style attributes as they can only contain `property: value` declarations.

The only way to apply styles to an element only in certain media is with a separate rule in your stylesheet, which means you'll need to come up with a selector for it.

### What CSS combinator do you if you have to select direct child of a parent ?

ParentHTMLTag > childHtmlTag

##### CSS

---

### What CSS combinator do you if you have to select adjacent siblings inside a parent?

- combinator
<ul>
  <li>One</li>
  <li>Two!</li>
  <li>Three</li>
</ul>

li + li {
color: red;
}

Will make two and three has red

##### CSS

---

### What CSS combinator do you if you have to first occurrence of element?

first-of-type selects the first of type element followed by + selects the adjacent sibling

```html
<ul>
  <li>One</li>
  <li>Two!</li>
  <li>Three</li>
</ul>
```

li:first-of-type{
color: red;
}

https://developer.mozilla.org/en-US/docs/Web/CSS/:first-of-type

##### CSS

---

### Why do you use box-sizing property ?

The CSS box-sizing property allows us to include the padding and border in an element's total width and height.

##### CSS

---

### Do you know about css clearfix ?

CSS clearfix is a hack to make the element larger to fit all of it's floating children

Let says A parent element div has 10px height and have few children
first child div has 20px height and
second child div has 40px height.

the child div overflow out of parent div, to fix this a clearfix is applied to parent div to expand and fix all of it's children.

https://stackoverflow.com/questions/8554043/what-is-a-clearfix

##### CSS

---

### Difference between CSS and CSS3 ?

##### CSS

---

### Advantages of using a a pre-processor like Sass ?

I did actually use in multiple projects and it being my favorite way of writing the CSS so far, 

SASS basically that lets you use variables, mathematical operations, mixins, loops, functions, imports, and other interesting functionalities that make writing CSS much more powerful and fun.

If I can say advantages I would say: 

1. Syntax Friendly - which means it lot easier to read and maintain the stylesheets
2. Variables - you can pretty define variables for every little thing like colors, font-sizes even padding which makes easy to change theming in larger applications
3. One Powerful thing about sass is the nested syntax which gives a visual hierarchy of the HTML semantics so it becomes naturally easy to maintain the styles 
   
I can go on about mixins which helps with avoid style repetition. 

There was one disadvantage of using sass in early times where the inspecting the elements on the browser did not reveal the computed styles but I think they got it fixed with recent versions of sass.

##### CSS,Frequently Asked

---

### What is CSS specificity?

CSS specificity is one of the issues if you do not see your styles applied to the element.

CSS Specificity is the set of the rules applied to CSS selectors in order to determine which style is applied to an element. The more specific a CSS style is, the higher point value it accrues, and the likelier it is to be present on the element's style.

The order of specificity is(from highest to lowest)
Style attribute => ID => Class => Elements

Mnemonic to remember `Super ICE`

More here: https://dev.to/emmawedekind/css-specificity-1kca
