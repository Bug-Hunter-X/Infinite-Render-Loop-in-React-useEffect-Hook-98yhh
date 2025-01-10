# React useEffect Infinite Render Loop Bug

This repository demonstrates a common bug in React applications: an infinite render loop caused by the `useEffect` hook.

## Bug Description

The `useEffect` hook, when used without a dependency array, runs after every render.  In this example, the effect logs the current count.  However, because the effect itself causes a re-render (by implicitly calling `setState` through any state updates within the component), it creates an infinite loop of renders.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the console for rapid logging and potential browser performance issues. 

## Solution

The solution involves adding a dependency array to the `useEffect` hook. This array specifies the values the hook should depend on. Only when one of these values changes will the effect run again. 
