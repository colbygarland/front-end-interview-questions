# Interview Questions

This is my collection of Front-end specific interview questions/concepts etc.

## React Questions

- What is React? What are the features of React?
    - React is a front-end JavaScript library developed by Facebook in 2011. It follows the component based approach which helps in building reusable UI components. It is used for developing complex and interactive web and mobile UI. Even though it was open-sourced only in 2015, it has one of the largest communities supporting it.
    - Major features of React are listed below:
        - It uses the virtual DOM instead of the real DOM.
        - It uses server-side rendering. ( new in Beta )
        - It follows uni-directional data flow or data binding.
- List some advantages of using React
    - It increases the application’s performance
    - It can be conveniently used on the client as well as server side
    - Because of JSX, code’s readability increases
    - React is easy to integrate with other frameworks like Meteor, Angular, etc
    - Using React, writing UI test cases become extremely easy
- What are some limitations of React?
    - React is just a library, not a full-blown framework
    - Its library is very large and takes time to understand
    - It can be little difficult for novice programmers to understand
    - Coding can get complex / hard to follow as it uses inline templating and JSX
- What is `render()` in React? And explain its purpose?
    - Each React class component must have a `render()` mandatorily. 
    - It returns a single React element which is the representation of the native DOM component. 
    - If more than one HTML element needs to be rendered, then they must be grouped together inside one enclosing tag such as <form>, <group>, <div> etc. 
    - This function must be kept pure i.e., it must return the same result each time it is invoked.
- What is virtual DOM?
    - The virtual DOM (VDOM) is an in-memory representation of Real DOM. 
    - The representation of a UI is kept in memory and synced with the “real” DOM. 
    - It’s a step that happens between the render function being called and the displaying of elements on the screen. 
    - This entire process is called reconciliation.
- Differentiate between Real DOM and Virtual DOM.
    - Real DOM
        - It updates slow.
        - Can directly update HTML.
        - Creates a new DOM if element updates.
        - DOM manipulation is very expensive.
        - Too much of memory wastage.
    - Virtual DOM
        - It updates faster.
        - Can’t directly update HTML.
        - Updates the JSX if element updates.
        - DOM manipulation is very easy.
        - No memory wastage.
- What do you understand by Virtual DOM? Explain its working.
    - A virtual DOM is a lightweight JavaScript object which originally is just the copy of the real DOM.
    - It is a node tree that lists the elements, their attributes and content as Objects and their properties. 
    - React’s `render` function (in class components) creates a node tree out of the React components. It then updates this tree in response to the mutations in the data model which is caused by various actions done by the user or by the system. 
    - This Virtual DOM works in three simple steps.
        1. Whenever any underlying data changes, the entire UI is re-rendered in Virtual DOM representation.
        2. Then the difference between the previous DOM representation and the new one is calculated.
        3. Once the calculations are done, the real DOM will be updated with only the things that have actually changed. 
- Describe how events are handled in React. 
    - In order to solve cross browser compatibility issues, your event handlers in React will be passed instances of SyntheticEvent, which is React’s cross-browser wrapper around the browser’s native event. 
    - These synthetic events have the same interface as native events you’re used to, except they work identically across all browsers.
    - What’s mildly interesting is that React doesn’t actually attach events to the child nodes themselves. 
    - React will listen to all events at the top level using a single event listener. 
    - This is good for performance and it also means that **React doesn’t need to worry about keeping track of event listeners when updating the DOM.**
- What is the difference between state and props? 
    - Both props and state are plain JavaScript objects. While both of them hold information that influences the output of `render`, they are different in their functionality with respect to component. i.e,
    - Props
        - Props get passed to the component similar to function parameters
        - Read-only
    - State
        - state is managed within the component similar to variables declared within a function.
- What are Higher-Order components? 
    - A higher-order component (HOC) is a function that takes a component and returns a new component. 
    - Basically, it’s a pattern that is derived from React’s compositional nature 
    - We call them as “pure’ components” because they can accept any dynamically provided child component but they won’t modify or copy any behavior from their input components.
- Why should not we update the state directly? 
    - If you try to update state directly then it won’t re-render the component.   Instead use `this.setState()` method. It schedules an update to a component’s state object. When state changes, the component responds by re-rendering
- What is StrictMode in React? 
    - React's StrictMode is sort of a helper component that will help you write better react components, you can wrap a set of components with <StrictMode /> and it'll basically:
        - Verify that the components inside are following some of the recommended practices and warn you if not in the console.
        - Verify the deprecated methods are not being used, and if they're used strict mode will warn you in the console.
        - Help you prevent some side effects by identifying potential risks.
- What is the difference between React Native and React?
    - React is a JavaScript library, supporting both front end web and being run on the server, for building user interfaces and web applications. 
    - On the other hand, React Native is a mobile framework that compiles to native app components, allowing us to build native mobile applications (iOS, Android, and Windows) in JavaScript that allows us to use ReactJS to build our components, and implements ReactJS under the hood. 
    - With React Native it is possible to mimic the behavior of the native app in JavaScript and at the end, we will get platform specific code as the output. 
    - We may even mix the native code with the JavaScript if we need to optimize our application further.
- How is React different from Angular?
    - React
        - Only the View of MVC
        - Server-side rendering
        - Uses virtual DOM
        - One-way data binding
        - Compile time debugging
        - Facebook
    - Angular
        - Complete MVC
        - Client-side rendering
        - Uses real DOM
        - Two-way data binding
        - Runtime debugging
        - Google
- What is Redux?
    - The basic idea of Redux is that the entire application state is kept in a single store. 
    - The store is simply a javascript object. 
    - The only way to change the state is by firing actions from your application and then writing reducers for these actions that modify the state. 
    - The entire state transition is kept inside reducers and should not have any side-effects.
    - Redux is based on the idea that there should be only a single source of truth for your application state, be it UI state like which tab is active or Data state like the user profile details.
    
        
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
- What do you understand by “Single source of truth”?


## Tips

- Leave time for feedback.
- Ask if they have questions for us.
