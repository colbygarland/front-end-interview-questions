# Interview Questions

This is my collection of Front-end specific interview questions/concepts etc.

## React Questions

- What is the difference between a class component vs. a functional component?
    - Class components are written by creating a JS class and extending React.Component
    - You must write a `render` function, and whatever UI the class will show gets returned from it
    - `this.setState()` to set/update state
    - Functional components are simply JS functions
    - Returns whatever UI needed by the function
    - Uses React hooks for state, effects, contexts, etc.
- How would you store state in a component?
    - In a class component, using `this.setState({state: 'value'})`
    - In a function component, using the `useState()` hook
- How would you share state between components? (global state)
    - Using React Context
    - Using global state libraries such as Redux, Mobx, Mobx-State-Tree, etc.
- Explain in your own words how React updates the UI.
    - React diffs the virtual DOM vs. the real DOM, and decides using it's algorithm what needs to be re-rendered
- How would you use a component in another component? 
    - Export the component you want to use
        - ex: `export const Component`
    - Import it in another file
        - ex: `import { Component } from '@/components/Component`
- How do you change a prop's value? 
    - You can't; props are read-only.
- What is JSX? 
    - JavaScript XML
    - Syntax extension to JS
    - JSX produces React elements
    - Embed any JS expression by wrapping with `{}`

## JavaScript Questions

- What is one way to avoid "callback hell"?
    - Promises
    - `async`/`await` (promise sugar syntax)
    - Code seperation
- How would you use a function in another file? 
    - `export function helloWorld(){}`
    - `import { helloWorld } from './hello-world'`
- What is a "default" import?
    - `export default function helloWorld(){}`
    - `import helloWorld from './hello-world'`
    - Puts the function in the global namespace
- What is TypeScript? Have you used it before?
    - TypeScript is an open-source language which builds on JavaScript, by adding static type definitions.
    - TypeScript code is transformed into JavaScript code via the TypeScript compiler or Babel.
- How do promises work in JavaScript? What about `async`/`await`?
    - Create a promise
    - Do your work
    - If success, resolve the promise
    - If error, reject the promise
    - Let's you do work and wait on the response
- Have you used any CSS frameworks? Which ones? Benefits? Drawbacks?
- What is SASS or LESS? Have you used either one before?
    - CSS extension language
    - Allows you to use variables, functions, mixins, nesting, partials, modules, extend/inheritance, operators (math)
- How would you store data so that it is still there after the user refreshes the page?
    - localStorage
- Explain in your own words the difference between a normal function and an arrow function. 
    - Shorter syntax
    - No binding of `this` 

## General Questions

- Have you worked with version control in the past?


## Tips

- Leave time for feedback.
- Ask if they have questions for us.
