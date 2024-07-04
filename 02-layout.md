Table of contents:
- [Flexbox \& Grid](#flexbox--grid)
  - [Flex](#flex)
    - [Flex-direction (`flex-direction`)](#flex-direction-flex-direction)
    - [Justify-content (`justify-content`)](#justify-content-justify-content)
    - [Align-items (`align-items`)](#align-items-align-items)
    - [Flex-wrap (`flex-wrap`)](#flex-wrap-flex-wrap)
  - [Grid](#grid)
    - [Grid-template-columns (`grid-template-columns`)](#grid-template-columns-grid-template-columns)
    - [Grid-template-rows (`grid-template-rows`)](#grid-template-rows-grid-template-rows)
    - [Grid-area (`grid-area`)](#grid-area-grid-area)
- [Block Element Modifier (BEM)](#block-element-modifier-bem)
  - [BEM In Practice](#bem-in-practice)
- [The Box Model](#the-box-model)
- [Positioning](#positioning)
- [Border Styles](#border-styles)
- [Background, Dropshadows, \& Cursors](#background-dropshadows--cursors)
  - [Background Image](#background-image)
  - [Dropshadow](#dropshadow)
  - [Cursors](#cursors)
    - [How do I put grab and grabbing to the same div?](#how-do-i-put-grab-and-grabbing-to-the-same-div)
- [Pseudo-Classes, Pseudo-Elements, \& Transitions](#pseudo-classes-pseudo-elements--transitions)
  - [Pseudo-Classes](#pseudo-classes)
    - [General Pseudo-Classes](#general-pseudo-classes)
    - [Location Pseudo-Classes](#location-pseudo-classes)
    - [Resource State Pseudo-Classes](#resource-state-pseudo-classes)
    - [Tree-Structural Pseudo-Classes](#tree-structural-pseudo-classes)
    - [User Action Pseudo-Classes](#user-action-pseudo-classes)
  - [Pseudo-Elements](#pseudo-elements)
  - [Transitions](#transitions)

# Flexbox & Grid

## Flex

Flexbox is a layout model that allows you to design a layout in one dimension. It is a powerful tool for creating responsive layouts. Flexbox is a one-dimensional layout method for laying out items in rows or columns. Items flex to fill additional space and shrink to fit into smaller spaces.

### Flex-direction (`flex-direction`)
- `row`: Items are placed the same as the text direction
- `row-reverse`: Items are placed opposite to the text direction
- `column`: Items are placed top to bottom
- `column-reverse`: Items are placed bottom to top

### Justify-content (`justify-content`)
- `flex-start`: Items are placed at the start of the main axis
- `flex-end`: Items are placed at the end of the main axis
- `center`: Items are centered along the main axis
- `space-between`: Items are evenly distributed in the main axis
- `space-around`: Items are evenly distributed with equal space around each item
- `space-evenly`: Items are distributed so that the spacing between any two items (and the space to the edges) is equal

### Align-items (`align-items`)
- `flex-start`: Items are placed at the start of the cross axis
- `flex-end`: Items are placed at the end of the cross axis
- `center`: Items are centered along the cross axis
- `stretch`: Items are stretched to fit the container

### Flex-wrap (`flex-wrap`)
- `no-wrap`: All items are on one line
- `wrap`: Items wrap around to additional lines
- `wrap-reverse`: Items wrap around to additional lines in reverse

## Grid

CSS Grid Layout is a two-dimensional layout system for the web. It lets you lay content out in rows and columns, and has many features that make building complex layouts straightforward.

### Grid-template-columns (`grid-template-columns`)
```css
.container {
  display: grid;
  grid-template-columns: 100px 100px 100px;
}
```

### Grid-template-rows (`grid-template-rows`)
```css
.container {
  display: grid;
  grid-template-rows: 100px 100px 100px;
}
```
We can combine both:
```css
.container {
  display: grid;
  grid-template-columns: 100px 100px 100px;
  grid-template-rows: 100px 100px 100px;
}
```

### Grid-area (`grid-area`)
```css
nav {grid-area: 1 / 1 / 2 / 3;}
aside {grid-area: 2 / 1 / 4 / 2;}
main {grid-area: 2 / 2 / 3 / 3;}
footer {grid-area: 3 / 2 / 4 / 3;}
```

It can be easier to use `grid-template-areas`:
```css
.container {
  display: grid;
  grid-template-columns: 100px 200px 100px;
  grid-template-rows: 100px 100px 100px;
  grid-template-areas:
    "header header header"
    "nav main aside"
    "footer footer footer";
}

header {grid-area: header;}
nav {grid-area: nav;}
main {grid-area: main;}
aside {grid-area: aside;}
footer {grid-area: footer;}
```

# Block Element Modifier (BEM)

Design mehotoology that helps you to create reusable components and code sharing in front-end development.

Methodologies:
- OOCSS
- SMACSS
- SUITCSS
- Atomic
- BEM

## BEM In Practice
`.block__element--modifier`

Example:

```html
<form class="form">
    <input class="form__input ...">
    <input class="form__input form__input--disabled ...">
    <button class="form__button form__button--large ...">Button</button>
</form>
```

```css
.form {...}
.form__input {...}
.form__input--disabled {...}
.form__button {...}
.form__button--large {...}
```

# The Box Model

![Box Model](/img/02-layout--box-model.png)

`box-sizing: border-box;`

# Positioning

- `static`: Default value. Elements are positioned according to the normal flow of the document
- `relative`: Elements are positioned relative to their normal position
- `absolute`: Elements are positioned relative to the nearest positioned ancestor
- `fixed`: Elements are positioned relative to the viewport
- `sticky`: Elements are positioned based on the user's scroll position

# Border Styles
- `solid`
- `dotted`
- `dashed`
- `double`
- `groove`
- `ridge`
- `inset`
- `outset`
- `none`
- `hidden`
- `mixed`

![Border styles](/img/02-layout--border-styles.png)

# Background, Dropshadows, & Cursors

## Background Image
- `background-image: url('...');`: Set the background image
- `background-repeat: no-repeat;`: Do not repeat the background image
- `background-size: cover;`: Resize the background image to cover the entire container
- `background-size: contain;`: Resize the background image to make sure the image is fully visible
- `background-size: 60% 40%;`: Resize the background image to 60% width and 40% height
- `background-position: center;`: Position the background image in the center
- `background-attachment: fixed;`: The background image will not scroll with the page
- `background-color: rgba(0, 0, 0, 0.5);`: Set the background color with an alpha value

## Dropshadow

- `filter: drop-shadow(8px 8px 10px rgba(16px, 14px, 10px, black));`: Add a drop shadow to an element
  - offset-x: 16px down (negative is up)
  - offset-y: 14px right (negative is left)
  - blur-radius: 10px (no negative value)
  - color: black

## Cursors

- `cursor: pointer;`: Change the cursor to a pointer when the user hovers over the element
- `cursor: not-allowed;`: Change the cursor to not-allowed when the user hovers over the element
- `cursor: grab;`: Change the cursor to a grab hand when the user hovers over the element
- `cursor: grabbing;`: Change the cursor to a grabbing hand when the user clicks on the element
- `cursor: url('...'), auto;`: Use a custom cursor

### How do I put grab and grabbing to the same div?

```css
div {
  cursor: grab;
}

div:active {
  cursor: grabbing;
}
```

# Pseudo-Classes, Pseudo-Elements, & Transitions

## Pseudo-Classes

### General Pseudo-Classes

- `:enabled`: Selects every enabled `<input>` element
- `:disabled`: Selects every disabled `<input>` element
- `:checked`: Selects every checked `<input>` element
- `:required`: Selects every required `<input>` element
- `:optional`: Selects every optional `<input>` element

### Location Pseudo-Classes

- `:link`: Selects unvisited links
- `:visited`: Selects visited links
- `:any-link`: Selects all links

### Resource State Pseudo-Classes

- `:playing`: Selects the current playing audio/video
- `:paused`: Selects the current paused audio/video

### Tree-Structural Pseudo-Classes

- `:root`: Selects the document's root element
- `:empty`: Selects any element that has no children
- `:nth-child(n)`: Selects every `<p>` element that is the `n` child of its parent
- `:nth-last-child(n)`: Selects every `<p>` element that is the `n` child of its parent, counting from the last child
- `:first-child`: Selects every `<p>` element that is the first child of its parent
- `:last-child`: Selects every `<p>` element that is the last child of its parent
- `:nth-of-type(n)`: Selects every `<p>` element that is the `n` child of its parent

### User Action Pseudo-Classes

- `:hover`: Selects links on mouse over
- `:active`: Selects the active link
- `:focus`: Selects the input element that has focus
- `:checked`: Selects every checked `<input>` element (for `checkboxes` and `radio buttons`)

## Pseudo-Elements

- `::after`: Insert content after the content of an element
- `::before`: Insert content before the content of an element
- `::first-letter`: Selects the first letter of every `<p>` element
- `::first-line`: Selects the first line of every `<p>` element
- `::placeholder`: Selects the placeholder text in an `<input>` element

## Transitions

- `transition-property`: Specifies the name of the CSS property the transition effect is for
- `transition-duration`: Specifies how many seconds or milliseconds a transition effect takes to complete
- `transition-timing-function`: Specifies the speed curve of the transition effect
- `transition-delay`: Defines when the transition effect will start
- `transition`: A shorthand property for setting the four transition properties (in that order)

Example:
```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 2s ease-in-out;
}

div:hover {
  width: 300px;
}
```