# ES6 Syntax and Feature Overview

## Variables and constant feature comparison

|Keyword|	Scope|	Hoisting|	Can Be Reassigned|	Can Be Redeclared|
|------|------|----------|----------|------------|
|var|	Function| scope	|Yes|	Yes	|Yes|
let|	Block |scope|	No|	Yes|	No|
|const	|Block| scope|	No|	No	|No|

## Variable declaration

- ES6 introduced the let keyword, which allows for block-scoped variables which cannot be hoisted or redeclared.

`var x = 0`

`let x = 0`

- Constant declaration
`
ES6 introduced the const keyword, which cannot be redeclared or reassigned, but is not immutable.

`const CONST_IDENTIFIER = 0`
` // constants are uppercase by convention`

- Arrow functions

The arrow function expression syntax is a shorter way of creating a function expression. Arrow functions do not have their own this, do not have prototypes, cannot be used for constructors, and should not be used as object methods.

```
function func(a, b, c) {} // function declaration
var func = function (a, b, c) {} // function expression
```

```
let func = (a) => {} // parentheses optional with one parameter
let func = (a, b, c) => {} // parentheses required with multiple parameter
```

- Template literals

    `var str = 'Release date: ' + date`
    `let str = 'Release Date: ${date}'`


- Key/property shorthand
ES6 introduces a shorter notation for assigning properties to variables of the same name.

```
var obj = {
  a: a,
  b: b,
}
```

```
let obj = {
  a,
  b,
}
```


## React - Hello World

The smallest React example looks like this:
```
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<h1>Hello, world!</h1>);
```

## JSX

`const element = <h1>Hello, world!</h1>;`

This funny tag syntax is neither a string nor HTML.

It is called JSX, and it is a syntax extension to JavaScript. We recommend using it with React to describe what the UI should look like. JSX may remind you of a template language, but it comes with the full power of JavaScript.

- React embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.

Let’s say there is a `<div>` somewhere in your HTML file:

`<div id="root"></div>`
We call this a “root” DOM node because everything inside it will be managed by React DOM.

Applications built with just React usually have a single root DOM node. If you are integrating React into an existing app, you may have as many isolated root DOM nodes as you like.

To render a React element, first pass the DOM element to ReactDOM.createRoot(), then pass the React element to root.render():

```
const root = ReactDOM.createRoot(
  document.getElementById('root')
);
const element = <h1>Hello, world</h1>;
root.render(element);
```


