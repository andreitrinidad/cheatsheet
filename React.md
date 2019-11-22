# React Cheatsheet

### Here lies my code snippets, own understanding and code snippets of React

> React JS? Okay watdaheal -- Andrei Trinidad, 2019

# Quick Links
* [JS 101](#js-101)
  * [Parameters vs. Arguments](#parameters-vs-arguments)
  * [Array Destructuring](#array-destructuring)
  * [Imports and Exports](#imports-and-exports)
  * [Fetching](#fetching)
  * [Promises](#promises)
* [React 101](#react-101)
  * [Hooks](#hooks)
  * [Styling](#styling)
* [Advanced React](#advanced-react)

# JS 101 
Things I found confusing and weird in JS that's always used in React.

___

## Parameters vs. Arguments
This is a parameter
```javascript
function myFunc (parameter1, parameter2) {
  //do something
}
```
This is an argument
```javascript 
myFunc(argument1, argument2); 
```
---

## Array Destructuring
Only advisable is array has two elements. A familiar pattern used in React useState hook.
```javascript
const myArray = [1, 2, 3];
const [theFirstElement, theSecondElement] = myArray;
console.log(theFirstElement); //1
console.log(theSecondElement); //2
```
What if I only like to destructure the second element in the array? Simple, just add a comma (```,```)

```javascript
  const [, theSecondElement] = myArray;
  console.log(theSecondElement); //2
```

---

## Imports and Exports
### Named exports
Named exports are like this:
```javascript
export function myFunc1() { //something... }
export function myFunc2() { //something... }
```
You can have multiple named exports in a single javascript file. So can import like this:
```javascript
import { myFunc1, myFunc2 } from './yourFile';
```
Use an alias to shorten import names
```javascript
import { mySuperLongImportName as foo } from './hakdog';
```
### Default Exports
A file can only have one default export
```javascript
const myExport = () => {
  //something...
}
export default myExport;
```
Import
```javascript
import myExport from './somewhere';

//or with named export
import someDefaultExport, { namedExport1, namedExport2 } from './somewhere';
```
> **TIP:** *Named and default exports can be used in a single file.*

---

## Fetching

<!-- Add some explanation here -->

### Doing multiple Fetch

Use [Promise.all](https://medium.com/r/?url=https%3A%2F%2Fteamtreehouse.com%2Flibrary%2Fmanage-multiple-requests-with-promiseall "Promise.all reference")

Heres a good pattern in using Promise.all

```javascript
const URLs = [
  'https://picsum.photos/id/1/1500/1500',
  'https://picsum.photos/id/2/1500/1500',
  'https://picsum.photos/id/3/1500/1500',
  'https://picsum.photos/id/4/1500/1500',
];
  
Promise.all(URLs.map(async urls => {
  return fetch(urls)
    .then(res => res.blob());
}))
  .then(values => values);
```
The example above is used for fetching multiple images. Idk why would you want to use this but this can be use in React Preloader

---

## Promises

🚧 *Under Construction*

---

## Blobs
Blobs are stream of data. Files can be converted into Blobs.
Here's an example of using blob.

---

# React 101
A list of coding tips, techniques and patterns to _**git gud**_ in React
## Goodbye Class-based Components
Don't even bother to learn how to use class-based components as there are now functional components. Thanks to **hooks**!
## Hooks
---
## useEffect
### Do something in _ComponentDidMount()_
```javascript
useEffect(() => { 
  //do something once
}, []);
```
Pass an empty array in the useEffect hook as a second argument

---
## useReducer
For complex state management

---
## Routing
Routing is not bundled in React. Manually add the react-router-dom package in yarn, npm or on your favorite package manager.
```javascript
import { BrowserRouter as Switch, Route, Link } from 'react-router-dom';
```
An example code on how to use routing
```html
<Switch>
  <Route exact path="/"></Route> 
  <Route path="/gallery">
  <Gallery />
  </Route>
</Switch>
```
### Okay but _watdaheal_ is the **exact** prop?

Routing works as like when it founds the closest path name possible for example:
```
/users
/users/create
```
The router will use ```/users``` if this was declared in the path but what if ```/users/create``` was written first? The router will use it as it is first declared. Obviously you can fix this by rearranging the ```<Route/>``` components. But you know for some reasons and just to be sure use the ```exact``` prop

### useParam

React Router version 5.1 introduces the [useParams](https://medium.com/r/?url=https%3A%2F%2Freacttraining.com%2Fblog%2Freact-router-v5-1%2F "useParams") hook.

### useHistory

---

## Styling
Now for the design part.

### Using a CSS preprocessor
Install the CSS preprocessor using yarn or npm then import your ```.css``` or ```.scss``` (or any other extension) and it will simply work.

### Styled Components

[Styled components](https://medium.com/r/?url=https%3A%2F%2Fwww.styled-components.com%2F "Styled Components website") are magic. Imagine writing your styles inside a template string inside your JSX file. All you have to do is wrap your component inside and wah-lah! It inherits the style you've just declared.

---
# Advanced React
## React Code Splitting 

Code Splitting is used for faster initial load by splitting each chunk of your app and compiling it only when needed. This is achievable using [React Loadable](https://medium.com/r/?url=http%3A%2F%2Fgithub.com%2Fjamiebuilds%2Freact-loadable "React Loadable docs").

### Use Cases
* If you want to load something before switching routes
* Add a loader component
* Preload a component

