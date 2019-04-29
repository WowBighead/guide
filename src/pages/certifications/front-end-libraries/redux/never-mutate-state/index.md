---
title: Never Mutate State
---
## Never Mutate State

This is a stub. <a href='https://github.com/freecodecamp/guides/tree/master/src/pages/certifications/front-end-libraries/redux/never-mutate-state/index.md' target='_blank' rel='nofollow'>Help our community expand it</a>.

<a href='https://github.com/freecodecamp/guides/blob/master/README.md' target='_blank' rel='nofollow'>This quick style guide will help ensure your pull request gets accepted</a>.

<!-- The article goes here, in GitHub-flavored Markdown. Feel free to add YouTube videos, images, and CodePen/JSBin embeds  -->

1.Create a new array using the ES6 method.

```redux.js
const { map } = Array.prototype;

const todos = [
  'Go to the store',
  'Clean the house',
  'Cook dinner',
  'Learn to code',
];
const newTodo = "Join freeCodeCamp to learn code freely";

let newTodos;

newTodos = [...todos,newTodo];
// or
newTodos = map.call(todos,todo => todo);
newTodos.push(newTodo);

console.log(newTodos) // ["Go to the store", "Clean the house", "Cook dinner", "Learn to code", "Join freeCodeCamp to learn code freely"] 
```
2.Return the new array (new state).
```redux.js

const ADD_TO_DO = 'ADD_TO_DO';

// A list of strings representing tasks to do:
const todos = [
  'Go to the store',
  'Clean the house',
  'Cook dinner',
  'Learn to code',
];

const immutableReducer = (state = todos, action) => {
  switch(action.type) {
    case ADD_TO_DO:
      return [...state,action.todo];
    default:
      return state;
  }
};

// an example todo argument would be 'Learn React',
const addToDo = (todo) => {
  return {
    type: ADD_TO_DO,
    todo
  }
}

const store = Redux.createStore(immutableReducer);
```
  
