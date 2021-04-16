## CSS Cheat Sheet

(Simple selectors)[https://www.w3schools.com/cssref/css_selectors.asp]

## Selectors

### ID selectors

Id (aka ID or Identifier) selectors are used to style an element with an id attribute like so.

Make note of the id attribute and the # at the start of the selector 

```html
<h1 id=”main-title”>Test</h1>
```

```css
#main-title {
  color: red
}
```

### Class selectors

Class selectors are multi-string values that can apply to one or more class of styles. A basic set of classes could look like this 

```html
<div class="container">
  <div class="box">
  </div>
  <div class="box is-red">
  </div>
</div>
```

```css
.container {
  margin-left: 2em;
  margin-right: 2em;
}

.box {
  background-color: blue;
  height: 200px;
  width: 100px;
}

.box.is-red {
  background-color: red;
}
```

> Make note of the above chain example `.box.is-red` this only applies to an element with both `box` and `is-red` classes in the `class` attribute like so `class="box is-red"`

### Elements selectors

html elements can be selected using css. This is done by writing the element name before your style block

```html
<ul>
  <li>First List Item</li>
</ul>
```

```css
ul {
  margin: 0;
  list-style-type: none;
}

li {
  color: red;
}
```
> In this example, all `li` elements will now have red text and all `ul` elements will have no margin and no bullet points

### Universal Selector

There is a way to select everything on a page (or in some cases decendants/children - I'll show this later)

```html
<div>
  <ul>
    <li>
      First List Item
    </li>
  </ul>
</div>
```

```css
* {
  padding: 20px;
}
```

> The above `*` applies to all elements in the example. Everything will have a padding of 20px!

## Special Selectors

### Attribute selectors

We can target elements but using their attributes values as conditions. For example

```html
<input name="first-name" type="text" placeholder="Enter your First Name"/>
<input name="email" type="email" placeholder="Please enter your Email Address"/>
```

```css
input[type="email"] {
  background: blue;
}
```

> The above example will result in only the the email input field having a blue background

#### Advanced attribute selection

A more advanced method is to use the regex selectors (I think that's what they're called?) to select certain parts of the attribute value

---|---|---|
`^=` | attribute must starts with | `a[href^="https"`
`$=` | attribute must end with | `a[href$=".jpg"]`
`*=` | attribute must container anywhere in string | `a[href*=".com"]`


### Child selectors

You can select children within an elements using `>`. This works like so 


```html 
<div class="header">
  <div class="box">
    <h1>Box in header</h1>
  </div>
  <div class="container">
    <div class="box">
      <h1>Box in container in header</h1>
    </div>
  </div>
</div>
```

```css
.header > .box h1 {
  color: red;
}
```

> In this example, only the first h1 in box will have red text. This is because the box class `.box` is a direct decendant (child) of `.header` specificed in the css with `.header > .box`

### Descendants

